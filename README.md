## Introduction ##
Use the python-pptx library to add chart support to the python-docx library.

## Example ##
```
from docx import Document
from pptx.chart.data import CategoryChartData
from pptx.util import Inches
from pptx.enum.chart import XL_CHART_TYPE

doc = Document()

labels = ["Jan", "Feb", "Mar"]
data = [25, 33, 18]
chart_data = CategoryChartData()
chart_data.categories = labels
chart_data.add_series("Title", data)
x, y, cx, cy = Inches(2), Inches(2), Inches(6), Inches(3)
chart = doc.add_chart(XL_CHART_TYPE.COLUMN_CLUSTERED, x, y, cx, cy, chart_data)


doc.save("t.docx")
```
