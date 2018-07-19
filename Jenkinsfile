import groovy.xml.MarkupBuilder
def ParseToHTMLTable(headers, params) {
  def writer = new StringWriter()
  new MarkupBuilder(writer).table() {
    tr {headers.each { title -> th(title) }}
    params.each { row ->
      tr {
        td(row.key)
        td(row.value)
      }
    }
  }
  return writer.toString()
}

def params = [
  "Job": "JobName",
  "isInQueue": true,
  "isBuilding": true,
  "isBuildBlocked": false,
  "Builds count": 15,
  "IsBuilding count": 1,
  "InProgress count": 1
]

println ParseToHTMLTable(["Parameter","Value"], params)