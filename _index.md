# CNS*2020 Workshop &ldquo;New interfaces for teaching with NEST&rdquo;

<script src="moment.js"></script>
<script src="moment-timezone-with-data.js"></script>

## Schedule

<script>
var start_time = moment.tz("2020-07-18 12:00", "Europe/Berlin");
</script>

<script>
document.write(moment().format());
</script>
<br><br>
<script>

document.write("<label for=\"tz-selector\">Timezone:</label>");
document.write("<select name=\"tz-selector\" id=\"tz-selector\" onChange=\"printTable(document.getElementById('schedule'), document.getElementById('tz-selector').value);\">");

moment.tz.names().forEach(function (item, index) {
	document.write("<option value=\"" + item + "\"");
	if (item.localeCompare("Europe/Berlin") == 0) {
		document.write(" selected=\"selected\"");
	}
	document.write(">" + item + "</option>");
});

document.write("</select>");

document.getElementById('tz-selector').value = "Europe/Berlin";
</script>

<script>
function printTable(el, in_tz) {
	//alert(in_tz);
	for (var i = 0; i < document.getElementsByClassName('timecell').length; ++i) {
		item = document.getElementsByClassName('timecell')[i];
		berlin_time = item.querySelector('noscript').innerHTML.replace(/^\s+|\s+$/g, '');
		//alert('old time: ' + berlin_time);
		//alert('attempted new time: ' + start_time.format("YYYY-MM-DD hh:mm:ss").slice(0, -8) + berlin_time + ":00");
		new_time = moment.tz(start_time.format("YYYY-MM-DD hh:mm:ss").slice(0, -8) + berlin_time + ":00", "Europe/Berlin").tz(in_tz);
		//alert('new time: ' + new_time.format());
		item.innerHTML = "<noscript>" + berlin_time + "</noscript>" + new_time.format('HH:mm');
	}
}
</script>


<div id="schedule" name="schedule">
<table>
<th>
<td>Time <noscript>(Berlin<br>timezone)</noscript></td>
<td>Description</td>
</th>
<tr>
<td class="timecell"><noscript>12:00</noscript>12:00</td>
<td>Welcome and introduction to the NEST Initiative</td>
</tr>
<tr>
<td class="timecell"><noscript>12:30</noscript>12:30</td>
<td>Hands-on with NEST Desktop</td>
</tr>
<tr>
<td class="timecell"><noscript>13:30</noscript>13:30</td>
<td>Lunch break/social</td>
</tr>
<tr>
<td class="timecell"><noscript>14:00</noscript>14:00</td>
<td>Hands-on running NEST from Jupyter Notebooks</td>
</tr>
<tr>
<td class="timecell"><noscript>15:00</noscript>15:00</td>
<td>(break for CNS2020 keynote by Matt Botvinick)</td>
</tr>
<tr>
<td class="timecell"><noscript>16:15</noscript>16:15</td>
<td>Introduction to NESTML</td>
</tr>
<tr>
<td class="timecell"><noscript>16:45</noscript>16:45</td>
<td>Hands-on with NESTML and Jupyter Notebooks</td>
</tr>
<tr>
<td class="timecell"><noscript>17:15</noscript>17:15</td>
<td>Hands-on with balanced network exercises</td>
</tr>
<tr>
<td class="timecell"><noscript>17:45</noscript>17:45</td>
<td>Coffee break/social</td>
</tr>
<tr>
<td class="timecell"><noscript>18:15</noscript>18:15</td>
<td>Hands-on with balanced network (continued)</td>
</tr>
<tr>
<td class="timecell"><noscript>19:00</noscript>19:00</td>
<td>Closing</td>
</tr>
</table>
</div>

## Description

NEST is established community software for the simulation of spiking neuronal network models capturing the full  detail  of  biological  network  structures  [1].  The  simulator  runs  efficiently  on  a  range  of  architectures  from  laptops  to  supercomputers  [2].  Many  peer-reviewed  neuroscientific  studies have used NEST as a simulation tool over the past 20 years. More recently, it has become a reference code for research on neuromorphic hardware systems [3].This tutorial provides hands-on experience with recent improvements of NEST. In the past, starting out with NEST could be challenging for computational neuroscientists, as models and simulations had to be programmed using SLI, C++ or Python. NEST Desktop changes this: It is an entirely graphical  approach  to  the  construction  and  simulation  of  neuronal  network  models.  It  runs  installation-free in the browser and has proven its value in several university courses. This opens the  domain  of  NEST  to  the  teaching  of  neuroscience  for  students  with  little  programming  experience.NESTML complements this new interface by enhancing the development process of neuron and synapse models. Advanced researchers often want to study specific features not provided by models already available in NEST. Instead of having to turn to C++, using NESTML they can write down differential equations and necessary state transitions in the mathematical notation they are used to. These descriptions are then automatically processed to generate machine-optimised code.After a quick overview of the current status of NEST and upcoming new functionality, the tutorial works  through  a  concrete  example  [4]  to  show  how  the  combination  of  NEST  Desktop  and  NESTML can be used in the modern workflow of a computational neuroscientist.

[1] https://nest-simulator.readthedocs.io/

[2] Jordan J., Ippen T., Helias M., Kitayama I., Sato M., Igarashi J., Diesmann M., Kunkel S. (2018) Extremely Scalable Spiking Neuronal Network Simulation Code: From Laptops to Exascale Computers. Frontiers in Neuroinformatics 12: 2

[3] Gutzen R., von Papen, M., Trensch G., Quaglio P. Grün S., Denker M. (2018) Reproducible Neural Network Simulations: Statistical Methods for Model Validation on the Level of Network Activity Data. Frontiers in Neuroinformatics 12 (90)

[4] Duarte R. & Morrison A. (2014). “Dynamic stability of sequential stimulus representations in adapting neuronal networks”, Front. Comput. Neurosci.