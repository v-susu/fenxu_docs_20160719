# Title is here

<div class="topic" xmlns="http://www.w3.org/1999/xhtml">
  <link type="text/css" rel="Stylesheet" href="..\branding1.css" />
  <div class="title">
            Walkthrough: Developing Web Sites Using Multiple Programming Languages
          </div>
  <!--Content type: DocStudio. Transform: webcollection2mtps.xslt.-->
  <div id="mainSection">
      <div id="mainBody">
        
        <p><!----></p>
    <p>By default, the App_Code folder does not allow multiple programming languages. However, you can modify your Web application structure and configuration settings to support multiple programming languages such as Visual Basic and C#. This allows ASP.NET to create multiple assemblies, one for each language. For more information, see <span class="linkTerms"><a class="mtps-external-link" href="../t990ks23_en-us_vs.80/t990ks23.md">Shared Code Folders in ASP.NET Web Sites</a></span>. Developers commonly include multiple programming languages in Web applications to support multiple development teams that operate independently and prefer different programming languages. </p>
    <p>This walkthrough explains the how to add multiple programming languages to an ASP.NET application.</p>
  <div class="collapsible-area"><span id="collapsible-area-title">Creating the Web Site</span><a id="sectionToggle0"><!----></a>
      <p>If you have already created a Web site in Visual Web Developer by completing <span class="linkTerms"><a class="mtps-external-link" href="https://msdn.microsoft.com/en-us/library/k4cbh4dh(v=vs.80).aspx">Walkthrough: Creating a Basic Web Page in Visual Web Developer</a></span>, you can use that Web site and go to the next section. Otherwise, create a new Web site and page by following these steps.</p>
      <h3 class="procedureSubHeading">To create a file system Web site</h3><div class="subSection"><ol><li>
            
              <p>Open Visual Web Developer.</p>
            
          </li><li>
            
              <p>On the <strong>File</strong> menu, click <strong>New</strong>, and then click <strong>Web Site</strong>. If you are using Visual Web Developer Express, on the <strong>File</strong> menu, click <strong>New</strong> <strong>Web Site</strong>.</p>
              <p>The <strong>New Web Site</strong> dialog box appears. </p>
            
          </li><li>
            
              <p>Under <strong>Visual Studio installed templates</strong>, click <strong>ASP.NET Web Site</strong>.</p>
            
          </li><li>
            
              <p>In the first <strong>Location</strong> box, select <strong>File System</strong>; in the second, enter the name of the folder where you want to keep the pages of your Web site. </p>
              <p>For example, type the folder name C:\WebSites\BulkUpdate.</p>
            
          </li><li>
            
              <p>In the <strong>Language</strong> list, click the programming language you prefer to work in.</p>
            
          </li><li>
            
              <p>Click <strong>OK</strong>.</p>
              <p>Visual Web Developer creates the folder and a new page named Default.aspx.</p>
            
          </li></ol></div>
    </div><div class="collapsible-area"><span id="collapsible-area-title">Creating Language-specific Classes</span><a id="sectionToggle1"><!----></a>
      <p>In this part of the walkthrough, you will create simple class files in two languages, Visual Basic and C#. </p>
      <h3 class="procedureSubHeading">To add language specific class files to the App_Code folder</h3><div class="subSection"><ol><li>
            
              <p>If your Web site does not already have an App_Code folder, do the following:</p>
              <ol><li>
                  <p>In Solution Explorer, select the name of the Web site.</p>
                </li><li>
                  <p>In the <strong>Website</strong> menu, click <strong>Add ASP.NET Folder</strong>, and then click <strong>App_Code</strong>. </p>
                </li></ol>
            
          </li><li>
            
              <p>In Solution Explorer, right-click the App_Code folder and then click <strong>New Folder</strong>.</p>
            
          </li><li>
            
              <p>Name the new folder "CSCode".</p>
            
          </li><li>
            
              <p>Select the CSCode folder. </p>
            
          </li><li>
            
              <p>In the <strong>Website</strong> menu, click <strong>Add New Item</strong>. </p>
              <p>The <strong>Add New Item</strong> dialog box is displayed.</p>
            
          </li><li>
            
              <p>In the <strong>Add New Item </strong>dialog box, choose the <strong>Class</strong> template, name the class "CSExample", select C# as the language, and click <strong>Add</strong>.</p>
            
          </li><li>
            
              <p>In Solution Explorer double-click the CSExample.cs file to open it.</p>
            
          </li><li>
            
              <p>Add the following code to the CSExample.cs file, overwriting the existing <code>CSExample</code> class already in the file:</p>
              <div class="CodeSnippetLanguage" xmlns="">C#<div class="codeSnippetContainerCodeContainer"><div class="CodeSnippetToolBarText" style="valign: top"></div><div id="CodeSnippetContainerCode_0" class="CodeSnippetContainerCode"><div style="color:Black;"><pre>
<span style="color:Blue;">public</span> <span style="color:Blue;">class</span> CSExample
{
    <span style="color:Blue;">private</span> <span style="color:Blue;">string</span> teamString;
    <span style="color:Blue;">public</span> cSharpExample()
    {
        TeamString = <span style="color:#A31515;">"C# Code"</span>;
    }
    <span style="color:Blue;">public</span> <span style="color:Blue;">string</span> TeamString 
    {
      <span style="color:Blue;">get</span> {
        <span style="color:Blue;">return</span> teamString;
      }
      <span style="color:Blue;">set</span> {
        teamString = value;
      }
    }
}
</pre></div></div></div></div>
            
          </li><li>
            
              <p>Create a folder and class for Visual Basic code by repeating steps 2-7 using the following values:</p>
              <ul><li>
                  <p>New folder: VBCode</p>
                </li><li>
                  <p>New class file: <code>VBExample</code></p>
                  <div class="alert"><table><tr><th><!--src=[../local/note.gif]--><img class="mtps-img-src" alt="Note" src="IC103139.gif" />Note </th></tr><tr><td>
                    <p>Be sure to set the language to Visual Basic when creating the new Visual Basic class file.</p>
                  </td></tr></table></div>
                </li></ul>
            
          </li><li>
            
              <p>Add the following code to the VBExample.vb file, overwriting the existing <code>VBExample</code> class already in the file:</p>
              <div class="CodeSnippetLanguage" xmlns="">VB<div class="codeSnippetContainerCodeContainer"><div class="CodeSnippetToolBarText" style="valign: top"></div><div id="CodeSnippetContainerCode_0" class="CodeSnippetContainerCode"><div style="color:Black;"><pre>
<span style="color:Blue;">Public</span> <span style="color:Blue;">Class</span> VBExample
    <span style="color:Blue;">Private</span> teamStr <span style="color:Blue;">As</span> <span style="color:Blue;">String</span>
    <span style="color:Blue;">Public</span> <span style="color:Blue;">Sub</span> <span style="color:Blue;">New</span>()
        TeamString = <span style="color:#A31515;">"Visual Basic Code"</span>
    <span style="color:Blue;">End</span> <span style="color:Blue;">Sub</span>
    <span style="color:Blue;">Public</span> <span style="color:Blue;">Property</span> TeamString() <span style="color:Blue;">As</span> <span style="color:Blue;">String</span>
        <span style="color:Blue;">Get</span>
            <span style="color:Blue;">Return</span> teamStr
        <span style="color:Blue;">End</span> <span style="color:Blue;">Get</span>
        <span style="color:Blue;">Set</span>(<span style="color:Blue;">ByVal</span> Value <span style="color:Blue;">As</span> <span style="color:Blue;">String</span>)
            teamStr = Value
        <span style="color:Blue;">End</span> <span style="color:Blue;">Set</span>
    <span style="color:Blue;">End</span> <span style="color:Blue;">Property</span>
<span style="color:Blue;">End</span> <span style="color:Blue;">Class</span>
</pre></div></div></div></div>
            
          </li></ol></div>
    </div><div class="collapsible-area"><span id="collapsible-area-title">Modifying the Web.config File</span><a id="sectionToggle2"><!----></a>
      <p>After creating separate subfolders for each programming language, you must change the Web site configuration so that ASP.NET will compile the subfolders separately.</p>
      <h3 class="procedureSubHeading">To modify the Web.config file to support multiple programming languages</h3><div class="subSection"><ol><li>
            
              <p>In Solution Explorer, select the name of the Web site.</p>
            
          </li><li>
            
              <p>If your Web site does not already have a Web.config file, do the following:</p>
              <ol><li>
                  <p>In the <strong>Website</strong> menu, click <strong>Add New Item</strong>. </p>
                </li><li>
                  <p>Choose <strong>Web Configuration File</strong> and then click <strong>Add</strong>.</p>
                </li></ol>
            
          </li><li>
            
              <p>Double-click the Web.config file to open it.</p>
            
          </li><li>
            
              <p>Modify the <strong>&lt;compilation&gt;</strong> section to include a <strong>&lt;codeSubDirectories&gt;</strong> node by copying the following section and pasting it as a child node of the &lt;<strong>compilation</strong>&gt; section:</p>
              <div class="CodeSnippetLanguage" xmlns=""><div class="codeSnippetContainerCodeContainer"><div class="CodeSnippetToolBarText" style="valign: top"></div><div id="CodeSnippetContainerCode_0" class="CodeSnippetContainerCode"><div style="color:Black;"><pre>
&lt;codeSubDirectories&gt;
  &lt;add directoryName="CSCode"/&gt;
  &lt;add directoryName="VBCode"/&gt;
&lt;/codeSubDirectories&gt;
</pre></div></div></div></div>
              <div class="alert"><table><tr><th><!--src=[../local/note.gif]--><img class="mtps-img-src" alt="Note" src="IC103139.gif" />Note </th></tr><tr><td>
                <p>Any definition of this section in Machine.config is overridden by the settings in the Web.config file. Also, the order of the configuration entries is the order that these entries will be created and linked.</p>
              </td></tr></table></div>
            
          </li></ol></div>
    </div><div class="collapsible-area"><span id="collapsible-area-title">Testing the Classes</span><a id="sectionToggle3"><!----></a>
      <p>You can now test that your Web site can use classes in both programming languages.</p>
      <h3 class="procedureSubHeading">To see the results of using multiple programming languages</h3><div class="subSection"><ol><li>
            
              <p>If your Web site does not already have a Default.aspx page, do the following:</p>
              <ol><li>
                  <p>In Solution Explorer, right-click the Web site name and then click <strong>Add New Item</strong>.</p>
                </li><li>
                  <p>Select <strong>Web Form</strong>, name the page "Default.aspx" and then click <strong>Add</strong>.</p>
                </li></ol>
            
          </li><li>
            
              <p>In Solution Explorer double-click the Default.aspx page. </p>
            
          </li><li>
            
              <p>Add a <strong>Button</strong> control to the Default.aspx page. </p>
            
          </li><li>
            
              <p>Set the <strong>Button</strong> control's text to "Class Language" and the ID of the button to "classLanguage".</p>
            
          </li><li>
            
              <p>Add a <strong>Label</strong> control to the Default.aspx page, set its <strong>ID</strong> property to "classLabel", and clear its <strong>Text</strong> property.</p>
            
          </li><li>
            
              <p>In Design view, double-click the <strong>Button</strong> control to create an event handler for its <strong>Click</strong> event. </p>
            
          </li><li>
            
              <p>Add the following code to the <code>classLanguage_Click</code> handler:</p>
              <div class="CodeSnippetLanguage" xmlns="">C#<div class="codeSnippetContainerCodeContainer"><div class="CodeSnippetToolBarText" style="valign: top"></div><div id="CodeSnippetContainerCode_0" class="CodeSnippetContainerCode"><div style="color:Black;"><pre>
CSExample CSCode = <span style="color:Blue;">new</span> CSExample();
VBExample VBCode = <span style="color:Blue;">new</span> VBExample();
<span style="color:Blue;">if</span> (classLabel.Text == CSCode.TeamString.ToString())
{
    classLabel.Text = VBCode.TeamString.ToString();
}
<span style="color:Blue;">else</span>
{
    classLabel.Text = CSCode.TeamString.ToString();
}
</pre></div></div></div></div>
              <p>
              </p>
              <div class="CodeSnippetLanguage" xmlns="">VB<div class="codeSnippetContainerCodeContainer"><div class="CodeSnippetToolBarText" style="valign: top"></div><div id="CodeSnippetContainerCode_0" class="CodeSnippetContainerCode"><div style="color:Black;"><pre>
<span style="color:Blue;">Dim</span> CSCode <span style="color:Blue;">As</span> CSExample =  <span style="color:Blue;">New</span> CSExample() 
<span style="color:Blue;">Dim</span> VBCode <span style="color:Blue;">As</span> VBExample =  <span style="color:Blue;">New</span> VBExample() 
<span style="color:Blue;">If</span> classLabel.Text = CSCode.TeamString.ToString() <span style="color:Blue;">Then</span>
    classLabel.Text = VBCode.TeamString.ToString()
<span style="color:Blue;">Else</span> 
    classLabel.Text = CSCode.TeamString.ToString()
<span style="color:Blue;">End</span> <span style="color:Blue;">If</span>
</pre></div></div></div></div>
            
          </li><li>
            
              <p>In Solution Explorer, right-click Default.aspx and select <strong>Set As Start Page</strong>.</p>
            
          </li><li>
            
              <p>Run the Web site and press the "Class Language" button to toggle between the two different language classes.</p>
            
          </li></ol></div>
    </div><div class="collapsible-area"><span id="collapsible-area-title">See Also</span><a id="seeAlsoToggle"><!----></a><h4 class="subHeading">Reference</h4><span class="linkTerms"><a class="mtps-external-link" href="https://msdn.microsoft.com/en-us/library/s10awwz0(v=vs.80).aspx">compilation Element (ASP.NET Settings Schema)</a></span><br /><h4 class="subHeading">Concepts</h4><span class="linkTerms"><a class="mtps-external-link" href="../t990ks23_en-us_vs.80/t990ks23.md">Shared Code Folders in ASP.NET Web Sites</a></span><br /><span class="linkTerms"><a class="mtps-external-link" href="https://msdn.microsoft.com/en-us/library/ms178473(v=vs.80).aspx">ASP.NET Application Life Cycle Overview</a></span><br /><span class="linkTerms"><a class="mtps-external-link" href="https://msdn.microsoft.com/en-us/library/399f057w(v=vs.80).aspx">ASP.NET Web Site Precompilation Overview</a></span><br /><br /></div></div>
      <!--remove copyright (HTML)-->
    </div>
</div>
