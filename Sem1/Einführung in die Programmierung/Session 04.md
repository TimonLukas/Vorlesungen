# Session 4

## Wahrheitswerte-Tabelle
* int a = 10;
* int b = 5;
* boolean z = false;

| Ausdruck | Wahrheitswert |
|----------|---------------|
|!z|true|
|a < 20|true|
|a == 2 * b|true|
|a % b != 0|false|
|(a > b) && z|false|
|(a > b) &vert;&vert; z |true|
|!(a < b) ^ !z |false|
|(a < b) &vert;&vert; ((a % 3 < b) && !z) |true|
