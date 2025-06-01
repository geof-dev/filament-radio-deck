# Modifications to add colors

- resources/views/forms/components/radio-deck.blade.php

```php
$color = $getColor($value);
```

- src/Forms/Components/RadioDeck.php

```php
protected array|Arrayable|Closure|string $colors = [];

public function getColors(): mixed
    {
        $colors = $this->evaluate($this->colors);

        if ($colors instanceof Arrayable) {
            $colors = $colors->toArray();
        }

        return $colors;
    }

    public function getColor($value): ?string
    {
        return $this->getColors()[$value] ?? null;
    }
```
