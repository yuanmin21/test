import groovy.xml.MarkupBuilder


def params = [
  "Job": "JobName",
  "isInQueue": true,
  "isBuilding": true,
  "isBuildBlocked": false,
  "Builds count": 15,
  "IsBuilding count": 1,
  "InProgress count": 1
]

import groovy.xml.MarkupBuilder
@NonCPS
def ParseToHTMLTable(headers, params) {
  def writer = new StringWriter()
  new MarkupBuilder(writer).table() {
    delegate.tr {headers.each { title -> delegate.delegate.th(title) }}
    params.each { row ->
      delegate.delegate.tr {
        delegate.td(row.key)
        delegate.td(row.value)
      }
    }
  }
  return writer.toString()
}
println ParseToHTMLTable(["Parameter","Value"], params)