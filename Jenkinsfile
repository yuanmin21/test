import groovy.xml.MarkupBuilder
def writer = new java.io.StringWriter()
def xml = new groovy.xml.MarkupBuilder(writer) 

xml.records() { 
    car(name:'HSV Maloo', make:'Holden', year:2006) {
        country('Australia')
        record(type:'speed', 'Production Pickup Truck with speed of 271kph')
    }
    car(name:'Royale', make:'Bugatti', year:1931) {
        country('France')
        record(type:'price', 'Most Valuable Car at $15 million')
    }
}

def records = new XmlSlurper().parseText(writer.toString()) 

println "==="
println writer

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