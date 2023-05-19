# al40000.github.io
# 3D model viewer

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wrapping Glia</title>
    <script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/3.1.1/model-viewer.min.js"></script>
    <style>
        #container {
            height: 600px;
            width: 600px;
            position: relative;
            margin:auto;
            background: #f7f7f7;
        }
        #aSide {
            height: 600px;
            width: 600px;
            position: absolute;
            top: calc(50% - 250px);
            margin-left: auto;
            margin-right: auto;
        }
        #aSide model-viewer{          
            width: 600px;
            height: 600px;
            position: absolute;
            top: 0;
            left: 0;
            border: none;
        }
        

    </style>
</head>
<body>
    <!--Main Container-->
    <div id="container">
        <div id="aSide">
            <model-viewer id= "neutral-lighting" id="color" camera-controls touch-action="pan-y"src="assests\fixedwrappingglia.glb" >
                <label for="neutral">Neutral Lighting: </label>
                <input id="neutral" type="checkbox" checked="true">
            </model-viewer>
        </div>

    </div>
   
    <script>
        (() => {
          const modelViewer = document.querySelector('#neutral-lighting');
          const checkbox = document.querySelector('#neutral');
          
          checkbox.addEventListener('change',() => {
            modelViewer.environmentImage = checkbox.checked ? '' : 'legacy';
          });
        })();
    </script>
</body>
</html>
