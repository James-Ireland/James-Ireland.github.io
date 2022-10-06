<!DOCTYPE html>
<html lang="en">
<head>
<title>James Ireland</title>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
* {
  box-sizing: border-box;
}

body {
  font-family: Arial, Helvetica, sans-serif;
}

/* Style the header */
header {
  background-color: #666;
  padding: 30px;
  text-align: center;
  font-size: 35px;
  color: white;
}

/* Create two columns/boxes that floats next to each other */
nav {
  float: left;
  width: 30%;
  height: 300px; /* only for demonstration, should be removed */
  background: #ccc;
  padding: 20px;
}

/* Style the list inside the menu */
nav ul {
  list-style-type: none;
  padding: 0;
}

article {
  float: left;
  padding: 20px;
  width: 70%;
  background-color: #f1f1f1; 
}

/* Clear floats after the columns */
section::after {
  content: "";
  display: table;
  clear: both;
}

/* Style the footer */
footer {
  background-color: #777;
  padding: 10px;
  text-align: center;
  color: white;
}

/* Responsive layout - makes the two columns/boxes stack on top of each other instead of next to each other, on small screens */
@media (max-width: 600px) {
  nav, article {
    width: 100%;
    height: auto;
  }
}
</style>
</head>
<body>

<header>
  <h2>Datasets</h2>
</header>

<section>
  <nav>
    <ul style="line-height:2;">
      <li><a href="https://james-ireland.github.io/">Main</a></li>
      
      <li><a href="https://james-ireland.github.io/Publications">Publications</a></li>
      
      <li><a href="https://james-ireland.github.io/Contact">Contact Information</a></li>
    </ul>
  </nav>
  
  <article>
    <h1>Synthetic Operating Room Table (SORT) Dataset</h1>
    <p>
      The Synthetic Operating Room Table (SORT) dataset is a largescale computer vision focused on instance counting, segmentation and localisation surgical instrument depictions placed on a table. 
      The depictions contained are rendered using the Unreal game engine and annotated leveraging the UnrealCV plugin (Qui, 2017). 
      SORT contains one container class, one material class (gauze) and six instrument classes namely, forceps, scalpels, pincettes (tweezers), syringes, periotomes, and scissors. 
      Each class contains two different 3D representations equally likely to be present for a given instance, with exception of the container class that leverages three different 3D models. 
      In total, we generated 89,838 images, split into 60% training (53,906), 20% validation (17,965), and 20% test (17,967), containing 365,469, 121,951 and 122,142 separate object instances, respectively. 
      The aim is to be able to count surgical instruments and materials via computer vision to aid medical staff in ensuring no instrument is retained by a patient, leading to complications such as chronic pain and sepsis. 
      Currently this is done manually, with the World Health Organisation (WHO) proposing that manual counts should be completed by two members of staff (Biswas, 2012), typically counting instruments laid out on a surface, either before or after their use. 
      This standard practice of logging the type and number of a given instrument or material to be used during an operation is not managerial overhead but crucial for the prevention of retained instruments, consumables, or materials during surgery, as these would negatively impact on a patient's recovery time or even lead to the patient's death. 
      ![alt text](https://james-ireland.github.io/blob/master/figures/SORT_image.png "....")
      ```bibtex
      Qiu, W., Zhong, F., Zhang, Y., Qiao, S., Xiao, Z., Kim, T.S. and Wang, Y., 2017, October. Unrealcv: Virtual worlds for computer vision. In Proceedings of the 25th ACM international conference on Multimedia (pp. 1221-1224) 
      
      R. Biswas, S. Ganguly, M. Saha, S. Saha, S. Mukherjee, and A. Ayaz. Gossypiboma and Surgeon - Current Medicolegal Aspect – A Review. Indian Journal of Surgery, 74(4):318–322, 2012 (2022-10-06) 
      ```
    </p> 
    
    <h1>Multiple Sensor Multi-instance (MSMI) Dataset</h1>
    <p>
      COMING SOON....
    </p> 
  </article>
</section>

<footer>
   
</footer>

</body>
</html>

