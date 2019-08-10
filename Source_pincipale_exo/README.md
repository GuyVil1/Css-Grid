# Tous les snippets CSS utilisé dans la formation

## Bases

``` css
.grid {
  display: grid;
  grid-template-columns: 150px 150px 150px;
  grid-template-rows: 200px 150px;
  grid-auto-rows: 100px;
  /* grid-column-gap: 50px;
  grid-row-gap: 50px; */
  grid-gap: 30px;
}
```

## Unité fr

``` css
.grid {
  display: grid;
  /* grid-template-columns: 1fr 1fr 1fr; */
  grid-template-columns: 2fr 1fr 200px;
  grid-gap: 30px;
}
```

## Repeat

``` css
.grid {
  display: grid;
  grid-template-columns: 150px repeat(3, 1fr 2fr);
  grid-gap: 30px;
}
```

## MinMax

``` css
.grid {
  display: grid;
  grid-template-columns: minmax(150px, 300px) 1fr 1fr;
  grid-gap: 30px;
  grid-auto-rows: minmax(100px, auto);
}
```

## Autoflow et Order

``` css
.grid {
  display: grid;
  /* grid-template-columns: repeat(3, 1fr); */
  grid-template-rows: repeat(3, 150px);
  grid-gap: 30px;
  /* grid-auto-flow: row; */
  grid-auto-flow: column;
}

.grid div {
  order: 3;
}

.grid div:nth-child(2) {
  order: 1;
}

.grid div:nth-child(1) {
  order: 2;
}
```

## Autofill Autofit

``` css
.grid {
  display: grid;
  /* grid-template-columns: repeat(auto-fill, 150px); */
  /* grid-template-columns: repeat(auto-fill, minmax(50px, 1fr)); */
  grid-template-columns: repeat(auto-fit, minmax(50px, 1fr));
  grid-gap: 30px;
}
```

## Alignements des enfants

``` css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: minmax(150px, auto);
  grid-gap: 30px;
  justify-items: center;
  align-items: center;
}

.grid div:nth-child(1) {
  justify-self: start;
  align-self: end;
}
.grid div:nth-child(6) {
  justify-self: start;
  align-self: start;
}
```

## Taille des enfants

``` css
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: minmax(150px, auto);
  grid-gap: 30px;
}

.start {
  grid-column: 1/3;
  grid-row: 1/3;
}

.end {
  grid-row: 2/4;
}
```

## Templates

``` css
header {
  grid-area: header;
}

article {
  grid-area: content;
}

aside {
  grid-area: sidebar;
}

footer {
  grid-area: footer;
}

.grid {
  width: 100%;
  max-width: 960px;
  margin: 0 auto;
  display: grid;
  grid-gap: 20px;
  grid-template-areas: 
    "header"
    "content"
    "sidebar"
    "footer"
}

@media (min-width: 550px) {
  .grid {
    grid-template-columns: 66.666666% 33.333333%;
    grid-template-areas: 
      "header header"
      "content sidebar"
      "footer footer"
  }
}

```