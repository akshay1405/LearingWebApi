Hello World1
function sendEmail() {
            debugger;
            
            var dashboard = _spPageContextInfo.siteAbsoluteUrl;
            var from = 'no-reply@sharepointonline.com'
            var to = 'JMLSupport';
            var body = BuildBody();
            var subject = "JML New Bug" ;
            var siteurl = _spPageContextInfo.webServerRelativeUrl;
            var urlTemplate = siteurl + "/_api/SP.Utilities.Utility.SendEmail";
            $.ajax({
                contentType: 'application/json',
                url: urlTemplate,
                type: "POST",
                data: JSON.stringify({
                    'properties': {
                        '__metadata': {
                            'type': 'SP.Utilities.EmailProperties'
                        },
                        'From': from,
                        'To': {
                            'results': [to]
                        },
                        'Body': body,
                        'Subject': subject
                    }
                }),
                headers: {
                    "Accept": "application/json;odata=verbose",
                    
