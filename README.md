# 1)Accordion
.accordion>(.item>p.number+p.text+svg.icon+.hidden-box>(p+ul>li*4))*3

```css
 .icon {width: 24px; height: 24px;
        stroke: #087f5b;
        /*Paints along the outline of the given graphical element and fill is use for interior point*/
      }

      .hidden-box ul {
        display: flex;
        flex-direction: column;
        gap: 12px;
        /* this will not give last element 12px at last li */
      }

      .hidden-box {
        grid-column: 2; /* make it in second column */
        display: none;
      }

      /* OPEN STATE */
      .open {
        border-top: 4px solid #087f5b;
      }

      .open .hidden-box {
        display: block;
      }

      .open .number,
      .open .text {
        color: #087f5b;
      }
```

# 2)Carousel
.carousel>(img+blockquote>(p.testimonial-text+p.testimonial-author+testimonial-job)+button(.btn-left>svg)+button(.btn-right>svg)+.dots)

```css
      .carousel {
        width: 800px;
        margin: 100px auto;
        background-color: #087f5b;
        padding: 32px 48px 32px 86px;
        /* making padding left 86px equal to gap 86 */
        border-radius: 8px;
        position: relative;

        display: flex;
        align-items: center;
        gap: 86px;
      }

    img {
        height: 200px;
        border-radius: 8px;
        transform: scale(1.5);
        box-shadow: 0 12px 24px rgba(0, 0, 0, 0.25);
      }

            /* CONTROLS */
      .btn {
        background-color: #fff;
        border: none;
        height: 40px;
        width: 40px;
        border-radius: 50%;/* 50% border-radius make square round */
        position: absolute;/* absolute to container class */
        box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
        cursor: pointer;

        display: flex;
        align-items: center;
        justify-content: center; /*make btn-icon inside center */
      }

      .btn--left {
        /* In relation to PARENTE ELEMENT */
        left: 0;
        top: 50%;
        /* In relation to ELEMENT ITSELF */
        transform: translate(-50%, -50%);/* make left outside  */
      }

      .btn--right {
        right: 0;
        top: 50%;
        transform: translate(50%, -50%);/* make right outside */
      }

      .btn-icon {
        height: 24px;
        width: 24px;
        stroke: #087f5b;
      }

       .dots {
        position: absolute;
        left: 50%;
        bottom: 0;
        transform: translate(-50%, 32px);
        /* make dots at bottom center with 32px from bottom */
        display: flex;
        gap: 12px;
      }

      .dot {
        height: 12px;
        width: 12px;
        background-color: #fff;
        border: 2px solid #087f5b;
        border-radius: 50%;
        cursor: pointer;
      }
```

# Tables
**emmet**
table>(thead>tr>th*4)+(tbody>(tr>th+td *3)*4)

```css
    table {
        width: 800px;
        margin-top: 100px;
        font-size: 18px;
        /* border: 1px solid #343a40; */
        border-collapse: collapse; 
        /* make 2 border apply single border */
      }

      th,
      td {
        /* border: 1px solid #343a40; */
        padding: 16px 24px;
        text-align: left;
      }

      thead tr {
        background-color: #087f5b;
        color: #fff;
      }

      thead th {
        width: 25%;
      }

      tbody tr:nth-child(odd) {
        background-color: #f8f9fa;
      }

      tbody tr:nth-child(even) {
        background-color: #e9ecef;
      }

```

# 4)Pagination

1. **emmet**
2. .pagination>(button.btn>svg.btn-icon)+a.page-link*6+span.dots+(button.btn>svg.btn-icon)

```css
    .pagination {
        display: flex;
        align-items: center;
        gap: 12px;
        margin-top: 200px;
      }
    .page-link:link,
      .page-link:visited {
        font-size: 18px;
        color: #343a40;
        text-decoration: none;
        height: 36px;
        width: 36px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
      }     
```

# 5)Hero section
1. **emmet code**
2. header>(nav.container>div{logo}+div{Navigation})+(.header-container>header-container-inner>h1+p+a)


```css


      header {
        height: 100vh;
        position: relative;
        /* stack of background image with linear gradient and url */
        background-image: linear-gradient(rgba(34, 34, 34, 0.6), rgba(34, 34, 34, 0.6)), url(hero.jpg);
        background-size: cover;
        color: #fff;
      }

.header-container {
        width: 1200px;
        position: absolute;

        /* In relation to PARENT size */
        left: 50%;
        top: 50%;

        /* In relation to ELEMENT size */
        transform: translate(-50%, -50%);
      }
```

#  6)App layout 
1. **emmet**
body>nav{Nav}+menu>button{New}*5+(section>.email*10)+main{Email view}+aside{Additional info}

```css
   body {
        font-family: sans-serif;
        color: #343a40;
        font-size: 24px;
        height: 100vh;
        /* full height of body */
        text-align: center;
        font-weight: bold;

        display: grid;
        /* 4 columns and 2 rows */
        grid-template-columns: 80px 400px 1fr 250px;
        grid-template-rows: 80px 1fr;
      }

      nav {
        background-color: #343a40;
        color: white;
        grid-row: 1 / -1;
        /* 80px column to all height */
      }


      menu {
        background-color: #7048e8;
        grid-column: 2 / -1;
        display: flex;
        align-items: center;
        gap: 12px;
        padding: 0 40px;
      }

      
      button:last-child {
        background-color: #d6336c;
        margin-left: auto;
      }


```