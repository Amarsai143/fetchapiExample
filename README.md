# fetchapiExample
fetch_api Example using javascript
<!DOCTYPE html>
<html lang="en">

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-9ndCyUaIbzAi2FUVXJi0CjmCapSmO7SnpJef0486qhLnuZ2cdeRhO02iuK6FUUVM" crossorigin="anonymous">

    <title>f1 fetch own</title>
    <style>
        img{
            width: 100px;
        }
    </style>
</head>
<body> 
    <h1 align="center"> welocme fetch api</h1>

    <div class="container">
        <table class="table table-bordered">
            <thead class="table-dark">
              <tr>
                <th scope="col">sno </th>
                <th scope="col">name</th>
                <th scope="col">price</th>
                <th scope="col">image</th>
              </tr>
            </thead>
            <tbody id="tableBody">
               
            </tbody>
          </table> 
    </div>
  
<script >
fetch("https://fakestoreapi.com/products").then((data)=>{
    //console.log(data);
    return data.json();// return to object
}).then((objectData)=>{
  // document.write(objectData[0].title);
    let tableData="";
    objectData.map((values)=>{
        tableData+=` <tr>
        <td>${values.title}</td>
        <td> ${values.description} </td>
         <td> ${values.price}</td>
         <td> <img src=" ${values.image}"/></td>
       </tr>`;
        document.getElementById("tableBody").innerHTML=tableData;
    })
})

</script>
    
</body>
</html>
