# Shreyas.m.s_Medical-and-the-Travel-Expense-Request


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Medical & Travel Expense Request</title>

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:Arial,Helvetica,sans-serif;
}

body{
background:#e8ecef;
padding:30px;
}

.container{
    width:95%;
    max-width:1200px;
    margin:30px auto;
    background:#fff;
    padding:25px;
    box-shadow:0 0 10px rgba(0,0,0,.2);
    overflow-x:auto;
}
.header{
display:flex;
justify-content:space-between;
align-items:center;
border-bottom:2px solid #ccc;
padding-bottom:20px;
margin-bottom:20px;
}

.logo{
display:flex;
align-items:center;
gap:15px;
}

.logo-box{
    width:200px;
    height:200px;
    display:flex;
    justify-content:center;
    align-items:center;
    background:white;
}

.logo-box img{
    width:100%;
    height:100%;
    object-fit:contain;
}
.address{
font-size:13px;
color:#555;
line-height:22px;
}

.title{
font-size:34px;
font-weight:bold;
color:#1d3557;
}

.claim{
border:2px solid #444;
padding:10px 20px;
text-align:center;
}

.claim h4{
font-size:15px;
margin-bottom:8px;
}

.claim h2{
color:#003366;
}

.section{
margin-top:30px;
}

.section-title{
background:#003366;
color:white;
padding:12px;
font-size:22px;
font-weight:bold;
}

.form-row{
    display:grid;
    grid-template-columns:repeat(auto-fit, minmax(180px, 1fr));
    gap:10px;
    padding:15px;
    background:#f5f5f5;
    align-items:center;
}

.form-row input,
.form-row select,
.form-row button{
    width:100%;
    box-sizing:border-box;
}

.form-row input{
padding:10px;
font-size:15px;
border:1px solid #bbb;
}

button{
background:#003366;
color:white;
border:none;
padding:10px 20px;
cursor:pointer;
font-size:15px;
}

button:hover{
background:#0a5dbb;
}

table{
    width:100%;
    border-collapse:collapse;
    margin-bottom:20px;
    table-layout:fixed;
    word-wrap:break-word;
}

table th,
table td{
    border:1px solid #bbb;
    padding:10px;
    text-align:center;
    word-break:break-word;
}

.delete{
background:red;
padding:7px 14px;
}

.footer{
margin-top:30px;
text-align:right;
}

.submit{
background:green;
padding:12px 30px;
font-size:18px;


@page{
    size: A4;
    margin: 15mm;
}

@media print{

    body{
        background:white;
        margin:0;
        padding:0;
    }

    .container{
        width:100%;
        max-width:100%;
        box-shadow:none;
        padding:0;
    }

    .page-break{
    display:block;
    height:0;
}

@media print{
    .page-break{
        page-break-before:always;
        break-before:page;
    }
}
    
    .section{
        page-break-inside: avoid;
        break-inside: avoid;
    }
}

.page-break{
    height:40px;
}

@media print{

    body{
        background:#fff;
        padding:0;
    }

    .container{
        width:100%;
        max-width:100%;
        margin:0;
        box-shadow:none;
        page-break-after:always;
        break-after:page;
    }

    .container:last-child{
        page-break-after:auto;
    }

    .section{
        page-break-inside:avoid;
        break-inside:avoid;
    }
}
}


@page{
    size:A4;
    margin:12mm;
}

@media print{

    body{
        background:#fff;
        padding:0;
        margin:0;
    }

    .container{
        width:100%;
        max-width:100%;
        margin:0;
        padding:15px;
        box-shadow:none;
    }

    .footer{
        margin-top:30px;
        display:flex;
        justify-content:space-between;
    }

    .section{
        page-break-inside:avoid;
        break-inside:avoid;
    }
}

</style>

</head>

<body>

<div class="container">

<div class="header">

<div class="logo">

<div class="logo-box">
    <img src="./logo.jpeg" alt="Company Logo">
</div>

<div class="address">
333 Broadway<br>
Winnipeg MB R3C 4W3<br>
Phone (204)954-4321<br>
Toll Free :1-855-954-4321
</div>

</div>

<div class="title">
Medical & Travel Expense Request
</div>

<div class="claim">
<h4>Claim No.</h4>
<h2>20042047</h2>
</div>

</div>

<p style="margin-bottom:20px;">
Madeleine Wilson requested reimbursement for the following medical and travel expenses.
</p>

<div class="section">

<div class="section-title">
Prescription Drugs
</div>

<div class="form-row">

<input id="drugName" placeholder="Drug Name">

<input type="date" id="purchaseDate">

<input type="date" id="prescriptionDate">

<input id="provider" placeholder="Healthcare Provider">

<input type="number" id="amount" placeholder="Paid Amount">

<button onclick="addPrescription()">
Add
</button>

</div>

<table id="prescriptionTable">

<tr>

<th>Drug Name</th>

<th>Date Purchased</th>

<th>Prescription Date</th>

<th>Healthcare Provider</th>

<th>Paid Amount</th>

<th>Action</th>

</tr>
<tbody>
</tbody>

</table>

</div>

<div class="section">

<div class="section-title">
Over-the-Counter Drugs
</div>

<div class="form-row">

<input id="otcDrug" placeholder="Drug Name">

<input type="date" id="otcDate">

<input type="number" id="otcAmount" placeholder="Paid Amount">

<input id="seller" placeholder="Seller Name">

<input id="reason" placeholder="Reason">

<button onclick="addOTC()">
Add
</button>

</div>

<table id="otcTable">

<tr>
<th>Drug Name</th>
<th>Date Purchased</th>
<th>Paid Amount</th>
<th>Seller</th>
<th>Reason</th>
<th>Action</th>
</tr>

<tbody>
</tbody>

</table>

</div>
<div class="section">

<div class="section-title">
Bandages, Braces or Other Medical Supplies
</div>

<div class="form-row">

<input id="itemName" placeholder="Item Purchased">

<input type="date" id="itemDate">

<input id="prescribed" placeholder="Was this Prescribed?">

<input id="healthProvider" placeholder="Healthcare Provider">

<input type="number" id="itemAmount" placeholder="Paid Amount">

<input id="itemSeller" placeholder="Seller Name">

<input id="itemReason" placeholder="Reason">

<button onclick="addSupply()">
Add
</button>

</div>

<table id="supplyTable">

<tr>

<th>Item Purchased</th>
<th>Date Purchased</th>
<th>Was this Prescribed?</th>
<th>Healthcare Provider</th>
<th>Paid Amount</th>
<th>Seller Name</th>
<th>Reason</th>
<th>Action</th>

</tr>

<tbody>
</tbody>

</table>

</div>



<div class="section">

<div class="section-title">
Parking for Medical Appointments
</div>

<div class="form-row">

<input id="facility" placeholder="Address of Healthcare Provider/Medical Facility">

<input type="date" id="parkingDate">

<input type="number" id="parkingAmount" placeholder="Paid Amount">

<input id="meterUsed" placeholder="Meter Used?">

<input id="meterNumber" placeholder="Meter Number">

<button onclick="addParking()">
Add
</button>

</div>

<table id="parkingTable">

<tr>

<th>Address of Healthcare Provider/Medical Facility</th>

<th>Date</th>

<th>Paid Amount</th>

<th>Meter Used?</th>

<th>Meter Number</th>

<th>Action</th>

</tr>

<tbody>

</tbody>

</table>

</div>


<div class="footer" style="display:flex;justify-content:flex-end;">
    <div>Page 1 of 2</div>
</div>

</div>

<div class="page-break"></div>

<div class="container">



<div class="section">

<div class="section-title">
Mileage to Medical Appointments
</div>

<p style="margin:15px 0;">
The WCB will generally reimburse only those transportation costs which are in excess of costs that would be incurred by the worker while travelling to and from work.
</p>

<div class="form-row">

<input type="date" id="appointmentDate">

<input id="healthAddress" placeholder="Address of Healthcare Provider/Medical Facility">

<input id="workAddress" placeholder="Address of Workplace">

<input type="number" id="roundTrip" placeholder="Round Trip (km)">

<input type="number" id="mileageAmount" placeholder="Paid Amount">

<button onclick="addMileage()">
Add
</button>

</div>

<table id="mileageTable">

<tr>

<th>Appointment Date</th>

<th>Address of Healthcare Provider/Medical Facility</th>

<th>Address of Workplace</th>

<th>Number of km (Round Trip)</th>

<th>Paid Amount</th>

<th>Action</th>

</tr>

<tbody>

</tbody>

</table>

</div>
<div class="section">

<div class="section-title">
Bus or Taxi Fare for Medical Appointments
</div>

<p style="margin:15px 0;">
<b>*Note:</b> Pre-approval is required from your WCB representative to claim taxi fare(s).
</p>

<div class="form-row">

<input type="date" id="travelDate">

<input id="startingPoint" placeholder="Address of Starting Point">

<input id="medicalFacility" placeholder="Address of Healthcare Provider/Medical Facility">

<select id="travelType">
<option value="">Bus/Taxi</option>
<option>Bus</option>
<option>Taxi</option>
</select>

<input type="number" id="fareAmount" placeholder="Total Fare Paid">

<button onclick="addTravel()">
Add
</button>

</div>

<table id="travelTable">

<tr>

<th>Appointment Date</th>
<th>Address of Starting Point</th>
<th>Address of Healthcare Provider/Medical Facility</th>
<th>Bus or Taxi</th>
<th>Total Fare Paid</th>
<th>Action</th>

</tr>

<tbody>
</tbody>

</table>

</div>

<div style="margin-top:30px;">

<label>
<input type="checkbox">
I understand that the <u>Privacy Notice</u> applies to the personal information collected in this document.
</label>

<!-- Privacy Notice -->
<div style="margin-top:30px;">
    <label>
        <input type="checkbox">
        I understand that the Privacy Notice applies...
    </label>
</div>

<!-- Submit Button -->
<div class="footer">
    <button class="submit" onclick="submitRequest()">
        Submit Request
    </button>
</div>


<div class="footer">
    <div>Worker App ID: 712041</div>
    <div>Submitted: March 21, 2026 5:43</div>
    <div>Page 2 of 2</div>
</div>




</div>


</div>

<script>

function addPrescription(){

let drug=document.getElementById("drugName").value;
let purchase=document.getElementById("purchaseDate").value;
let prescription=document.getElementById("prescriptionDate").value;
let provider=document.getElementById("provider").value;
let amount=document.getElementById("amount").value;

if(drug=="" || purchase=="" || prescription=="" || provider=="" || amount==""){
alert("Please fill all fields");
return;
}

let table=document.getElementById("prescriptionTable");

let row=table.insertRow(-1);

row.innerHTML=
"<td>"+drug+"</td>"+
"<td>"+purchase+"</td>"+
"<td>"+prescription+"</td>"+
"<td>"+provider+"</td>"+
"<td>$"+amount+"</td>"+
"<td><button class='delete' onclick='deleteRow(this)'>Delete</button></td>";

document.getElementById("drugName").value="";
document.getElementById("purchaseDate").value="";
document.getElementById("prescriptionDate").value="";
document.getElementById("provider").value="";
document.getElementById("amount").value="";

}

function addOTC(){

let drug=document.getElementById("otcDrug").value;
let date=document.getElementById("otcDate").value;
let amount=document.getElementById("otcAmount").value;
let seller=document.getElementById("seller").value;
let reason=document.getElementById("reason").value;

if(drug=="" || date=="" || amount=="" || seller=="" || reason==""){
alert("Please fill all fields");
return;
}

let table=document.getElementById("otcTable");

let row=table.insertRow(-1);
row.innerHTML=
"<td>"+drug+"</td>"+
"<td>"+date+"</td>"+
"<td>$"+amount+"</td>"+
"<td>"+seller+"</td>"+
"<td>"+reason+"</td>"+
"<td><button class='delete' onclick='deleteRow(this)'>Delete</button></td>";

document.getElementById("otcDrug").value="";
document.getElementById("otcDate").value="";
document.getElementById("otcAmount").value="";
document.getElementById("seller").value="";
document.getElementById("reason").value="";

}

function deleteRow(button){
let row = button.parentNode.parentNode;
row.parentNode.removeChild(row);
}
function submitRequest() {

    // Hide all input sections
    document.querySelectorAll(".form-row").forEach(function(row){
        row.style.display = "none";
    });
    document.querySelector("label").style.display = "none";
    document.querySelector(".submit").style.display = "none";
    document.querySelectorAll(".delete").forEach(function(btn){
        btn.style.display = "none";
    });
    document.querySelectorAll("table").forEach(function(table){

        if(table.rows.length > 0){
            table.rows[0].lastElementChild.style.display = "none";
        }

        for(let i=1;i<table.rows.length;i++){
            table.rows[i].lastElementChild.style.display = "none";
        }
    });

    document.querySelectorAll(".section").forEach(function(section){

        let table = section.querySelector("table");

        if(table && table.rows.length <= 1){
            section.style.display = "none";
        }

    });

    alert("Medical Expense Request Submitted Successfully!");
}
function addSupply(){

let item=document.getElementById("itemName").value;
let date=document.getElementById("itemDate").value;
let prescribed=document.getElementById("prescribed").value;
let provider=document.getElementById("healthProvider").value;
let amount=document.getElementById("itemAmount").value;
let seller=document.getElementById("itemSeller").value;
let reason=document.getElementById("itemReason").value;

if(item=="" || date=="" || prescribed=="" || provider=="" || amount=="" || seller=="" || reason==""){
alert("Please fill all fields");
return;
}

let table=document.getElementById("supplyTable");

let row=table.insertRow(-1);

row.innerHTML=
"<td>"+item+"</td>"+
"<td>"+date+"</td>"+
"<td>"+prescribed+"</td>"+
"<td>"+provider+"</td>"+
"<td>$"+amount+"</td>"+
"<td>"+seller+"</td>"+
"<td>"+reason+"</td>"+
"<td><button class='delete' onclick='deleteRow(this)'>Delete</button></td>";

document.getElementById("itemName").value="";
document.getElementById("itemDate").value="";
document.getElementById("prescribed").value="";
document.getElementById("healthProvider").value="";
document.getElementById("itemAmount").value="";
document.getElementById("itemSeller").value="";
document.getElementById("itemReason").value="";

}
function addParking(){

let facility=document.getElementById("facility").value;
let date=document.getElementById("parkingDate").value;
let amount=document.getElementById("parkingAmount").value;
let meter=document.getElementById("meterUsed").value;
let meterNo=document.getElementById("meterNumber").value;

if(facility=="" || date=="" || amount=="" || meter=="" || meterNo==""){
alert("Please fill all fields");
return;
}

let table=document.getElementById("parkingTable");

let row=table.insertRow(-1);

row.innerHTML=
"<td>"+facility+"</td>"+
"<td>"+date+"</td>"+
"<td>$"+amount+"</td>"+
"<td>"+meter+"</td>"+
"<td>"+meterNo+"</td>"+
"<td><button class='delete' onclick='deleteRow(this)'>Delete</button></td>";

document.getElementById("facility").value="";
document.getElementById("parkingDate").value="";
document.getElementById("parkingAmount").value="";
document.getElementById("meterUsed").value="";
document.getElementById("meterNumber").value="";

}
function addMileage(){

let appDate=document.getElementById("appointmentDate").value;
let health=document.getElementById("healthAddress").value;
let work=document.getElementById("workAddress").value;
let km=document.getElementById("roundTrip").value;
let amount=document.getElementById("mileageAmount").value;

if(appDate=="" || health=="" || work=="" || km=="" || amount==""){
alert("Please fill all fields");
return;
}

let table=document.getElementById("mileageTable");

let row=table.insertRow(-1);

row.innerHTML=
"<td>"+appDate+"</td>"+
"<td>"+health+"</td>"+
"<td>"+work+"</td>"+
"<td>"+km+" km</td>"+
"<td>$"+amount+"</td>"+
"<td><button class='delete' onclick='deleteRow(this)'>Delete</button></td>";

document.getElementById("appointmentDate").value="";
document.getElementById("healthAddress").value="";
document.getElementById("workAddress").value="";
document.getElementById("roundTrip").value="";
document.getElementById("mileageAmount").value="";

}
function addTravel(){

let date=document.getElementById("travelDate").value;
let start=document.getElementById("startingPoint").value;
let facility=document.getElementById("medicalFacility").value;
let type=document.getElementById("travelType").value;
let amount=document.getElementById("fareAmount").value;

if(date=="" || start=="" || facility=="" || type=="" || amount==""){
alert("Please fill all fields");
return;
}

let table=document.getElementById("travelTable");

let row=table.insertRow(-1);

row.innerHTML=
"<td>"+date+"</td>"+
"<td>"+start+"</td>"+
"<td>"+facility+"</td>"+
"<td>"+type+"</td>"+
"<td>$"+amount+"</td>"+
"<td><button class='delete' onclick='deleteRow(this)'>Delete</button></td>";

document.getElementById("travelDate").value="";
document.getElementById("startingPoint").value="";
document.getElementById("medicalFacility").value="";
document.getElementById("travelType").value="";
document.getElementById("fareAmount").value="";

}

</script>


</body>
</html>
