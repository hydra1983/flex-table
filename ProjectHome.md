
# Content #
## About this project ##
This project is established to create a word table like widget in Flex.

## API ##
Here is the APIs of classes Table, Row, and Cell.
  * <b>public class Table</b>
  1. `selectedCells:ArrayCollection ` <br>return the selected of the table.<br><br>
<ol><li><code>rows:Array</code> <br>return all the rows of the table.<br><br>
</li><li><code>cells:Array </code> <br>return all the cells of the table.<br><br>
</li><li><code>public static function createTable(width:int,numRows:int,numColumns:int):Table</code> <br>create a table with defined width, rows number and columns number.<br><br><i>Parameters:</i><br><code>int</code> width -- the width of the table to be created<br><code>int</code> numRows -- the number of the rows to be created.<br><code>int</code> numColumns -- the number of the cells to be created for each row.<br><br>
</li><li><code>public function getChildrenFrom(rowPosition:int,cellPosition:int):Array</code> <br>get all the children of the specified cell at the given position<br><br><i>Parameters:</i><br><code>int</code> rowPosition -- the position of the row contains the specified cell in the table.<br><code>int</code> cellPosition-- the position of the specified cell in the row.<br><br>
</li><li><code>public function removeChildrenFrom(rowPosition:int,cellPosition:int):void</code> <br>remove all the children from the specified cell<br><br><i>Parameters:</i><br><code>int</code> rowPosition -- the position of the row contains the specified cell in the table.<br><code>int</code> cellPosition-- the position of the specified cell in the row.<br><br>
</li><li><code>public function insertChildAt(child:UIComponent, rowPosition:int,cellPosition:int):void</code> <br>add a component into the specified cell.<br><br><i>Parameters:</i><br><code>UIComponent</code> child -- the component to be added into the cell.<br><code>int</code> rowPosition -- the position of the row contains the specified cell in the table.<br><code>int</code> cellPosition-- the position of the specified cell in the row.<br>
</li></ol><ul><li>public class Row<br>
</li></ul><ol><li><code>previous:Row</code> <br>return the previous row of the current one. if the current is the first row of the table, it returns a <code>null</code> object.<br><br>
</li><li><code>next:Row</code> <br>return the next row of the current one. if the current is the last row of the table, it returns a <code>null</code> object.<br><br>
</li><li><code>cells:Array </code> <br>return all the cells of the row.<br><br>
</li><li><code>position:int</code> <br>return the index of the row in the table' children  .<br><br>
</li></ol><ul><li>public class Cell<br>
</li></ul><ol><li><code>selected:Boolean</code> <br> indicates whether the cell is selected.<br><br>
</li><li><code>previous:Cell</code> <br>return the previous cell of the current one. if the current is the first cell of the parent row, it returns a <code>null</code> object.<br><br>
</li><li><code>next:Cell</code> <br>return the next cell of the current one. if the current is the last cell of the parent row, it returns a <code>null</code> object.<br><br>
</li><li><code>position:int</code> <br>return the index of the cell in the parent row' children  .<br><br></li></ol>

<h2>Demo</h2>
Here is a simple demo of the usage of this widget. The source is published as well.<br>
<br>
<a href='http://hydra1983.googlepages.com/FlextableRefined.html'>Let me have a look</a>
<h3>Screenshot</h3>

<a href='http://flex-table.googlecode.com/svn/trunk/doc/images/flex-table-demo-screenshot-1.JPG'>http://flex-table.googlecode.com/svn/trunk/doc/images/flex-table-demo-screenshot-1.JPG</a>

<a href='http://flex-table.googlecode.com/svn/trunk/doc/images/flex-table-demo-screenshot-2.JPG'>http://flex-table.googlecode.com/svn/trunk/doc/images/flex-table-demo-screenshot-2.JPG</a>

<h3>Description</h3>
<ol><li>insert controls <br>insert some flex controls into each cell of the specified table widget.<br><br>
</li><li>remove all controls <br>remove all the controls from each cell of the specified table widget.<br><br>
</li><li>remove controls from selected cell <br>remove all the controls from the selected cells of the specified table widget.<br><br>
</li><li>the operations of the table <br> (click right mouse button on anywhere of the table to show a context menu)<br>
</li></ol><ul><li><u>merge cells</u> <br> merge all the selected cells.<br><br>
</li><li><u>split cells</u> <br> split the selected cell.<br><br>
</li><li><u>Insert Columns to the Left</u> <br> insert several cells into the table widget on the left side of the top-left cell of the selected cells.<br><br>
</li><li><u>Insert Columns to the Right</u>  <br> insert several cells into the table widget on the right side of the top-right cell of the selected cells.<br><br>
</li><li><u>Insert Rows Above</u> <br> insert a row contained several cells into the table widget above the topmost selected cells.<br><br>
</li><li><u>Insert Rows Below</u> <br> insert a row contained several cells into the table widget below the bottommost selected cells.<br><br>
</li><li><u>Delete Entire Row</u> <br> delete the entire rows contains the selected cells.<br><br>
</li><li>select single cell <br> move the cursor over the table, when the cursor looks like <img src='http://flex-table.googlecode.com/svn/trunk/lib/src/com/siloon/containers/table/assets/cellSelectionIndicator.gif' />,click the left mouse button to select the target cell. Or directly click the right mouse button to select the target cell.<br><br>
</li><li>select multiple cells <br> select one cell, then press and hol SHIFT key to select another cell, the cells among the first cell and the last cell are all selected. Or press and hold CTRL key, you will select the target cells one by one.<br><br>
</li><li>select a row of cells <br> when the cursor looks like <img src='http://flex-table.googlecode.com/svn/trunk/lib/src/com/siloon/containers/table/assets/cellSelectionIndicator.gif' />, double the left mouse button.<br><br>
</li><li>select a column of cells <br> move the cursor to the top of the cells contained in the first row, when cursor looks like <img src='http://flex-table.googlecode.com/svn/trunk/lib/src/com/siloon/containers/table/assets/columnSelectionIndicator.gif' />, click the left mouse button.<br><br>
</li><li>deselect a cell <br> press and hold CTRL key and do what we do to select cell to deselect the target cell .<br><br>
</li><li>change cell width <br> when cursor looks like <img src='http://flex-table.googlecode.com/svn/trunk/lib/src/com/siloon/containers/table/assets/horizontalDelimiter.gif' />, click and hold left mouse button and move the appeared line to proper position in order to change the width of related cells. Select a cell first, and move the mouse to its border, then move the appeared line to proper position, you can merely change its width.<br><br>
</li><li>change cell height <br> when cursor looks like <img src='http://flex-table.googlecode.com/svn/trunk/lib/src/com/siloon/containers/table/assets/verticalDelimiter.gif' />, drag the appeared line to proper position to change the height of related cells.</li></ul>

<h3>Note</h3>
<blockquote>The "wmode" of your SWF using flex-table and embedded in html page should be "opaque", or the context menu won't work.</blockquote>

<h3>Related Projects</h3>
<a href='http://code.google.com/p/rightclickmanager/'>rightclickmanager</a>