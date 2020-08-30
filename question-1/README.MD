###### **Что выведет данный php код?**

```
    function foodAlphabet(string $char = 'C'): void
    {
        $result = (
            ($char == 'A') ? 'apricot' :
                ($char == 'B') ? 'bread' :
                    ($char == 'C') ? 'carrot' :
                        ($char == 'D') ? 'donut' :
                            ($char == 'E') ? 'egg' :
                                'zucchini'
        );
        echo $result;
    }
    foodAlphabet('B');
```