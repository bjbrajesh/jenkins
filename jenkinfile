pipeline {

agent any

/*Intializing Netstorm test configuration*/
environment {
def url = "https://lowes-digital-2.cavisson.com/"
def project = "default"
def subProject = "default"
def scenario = "StageMonitoringTestofPrometheus" //testsuite name will be given
def baselineTR = "-1" //Base line test run will be given as 1386
def report = " "
def testMode = "T"
def pollInterval = "20"
def profile = "system"
def generateReport = true
def doNotWaitForTestCompletion = false
//def cavToken="SdfALAydiNmefxWI8f2mdoM98VPPIFFwJJc3o0oMKqWaUkkF9x0Q88GCF%2FwfZHS%2F3qq2sV%2FH0ZIRU0XrMpi4Qk0gnfXPSC8IjLojs%2FKWyqAggg9R6kIKUJepp69ckOsCOMbdRuiEXX37qvtFyNaBsHB%2B2fsWGu74TK6UfAhgWuI%3D"
//def DataDirectory = "PASPerf4"
//def email = "mailto:email_ids_to_bharath.kumar@csaa.com"
skipSSLHostCheck = true
skipSSLCertCheck = true
}

stages {
stage('Execute Netstorm Test') {
steps {
script {
echo 'Executing Netstorm test'

//withCredentials([usernamePassword(credentialsId: 'NetstormCredential',usernameVariable: 'cavisson',passwordVariable: '@dmin')]) {
//withCredentials([usernamePassword(credentialsId: 'NetstormCredential',usernameVariable: 'USERNAME',passwordVariable: 'PASSWORD')]) {

step([$class: 'NetStormBuilder', URLConnectionString: url,username: 'cavisson', password: '@dmin' , project:project, subProject:subProject, scenario:scenario, testMode: testMode, baselineType:baselineTR,pollInterval:pollInterval,protocol:"",repoIp:"",repoPort:"",repoPath:"",repoUsername:"",repoPassword:"",profile:profile,script:"",page:"",advanceSett:"",urlHeader:"",hiddenBox:"",gitPull:"",
generateReport:generateReport, doNotWaitForTestCompletion:doNotWaitForTestCompletion, totalusers: "",rampUpSec: "",rampupmin: "",rampuphour:"",duration:"",serverhost:"", 
sla: "",testName:"",scriptPath:"", rampupDuration:"", 
emailid: "EMAIL_IDS_TO_brajesh.singh@cavisson.com,shivam.singh@cavisson.com", 
emailidCC: "EMAIL_IDS_CC_gaurav.baghel@cavisson.com",emailidBcc: "", testsuite: scenario,checkRuleFileUpload: "",skipSSLHostCheck:skipSSLHostCheck,skipSSLCertCheck:skipSSLCertCheck])

//testsuite: "${params.Testsuite}".toString()
// "${params.Email}".toString()
//emailid: email,
//emailid:"${params.Email}".toString(),
//dataDir:"${params.DataDirectory}".toString()
//}

}
}
}
}

post {
always {

// publish html
publishHTML target: [
allowMissing: false,
alwaysLinkToLastBuild: true,
keepAll: true,
reportDir: 'TestSuiteReport',
reportFiles: 'TestSuiteReportNS.html',
reportName: 'HTML Report'
]

}
}
}