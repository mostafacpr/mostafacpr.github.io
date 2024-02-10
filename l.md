
<!-- saved from url=(0084)https://farazgar.ir/Tools/General/Direct%20link%20Google%20Drive/Google%20Drive.html -->
<html lang="en"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

	
	<title>index</title>
  
	<style>

		@font-face {
		  font-family: Vazir;
		  src: url('https://cdn.fontcdn.ir/Font/Persian/Vazir/Vazir.eot');
		  src: url('https://cdn.fontcdn.ir/Font/Persian/Vazir/Vazir.eot?#iefix') format('embedded-opentype'),
			   url('https://cdn.fontcdn.ir/Font/Persian/Vazir/Vazir.woff2') format('woff2'),
			   url('https://cdn.fontcdn.ir/Font/Persian/Vazir/Vazir.woff') format('woff'),
			   url('https://cdn.fontcdn.ir/Font/Persian/Vazir/Vazir.ttf') format('truetype');
		  font-weight: normal;
		}
		
	body{
	    font-family: Vazir;
	}
		
		.h3style{
    background: #fff;
    position: relative;
    text-align: right;
    padding: 3px 20px 3px 20px;
    border-radius: 50px 15px;
    width: auto;
    display: inline-block;
    border-right: 5px solid #ff4784;
    z-index: 1;
    margin-top: 20px;
    margin-bottom: 10px;
    box-shadow: 0px 2px 2px #000;
			
		}
		
		.block{
			background:#fcfcfc;
			/*border:1px solid #ddd;*/
			border-radius:10px;
			padding:10px 20px;
			margin:10px;
			direction:rtl;
		}
		
		#linkpaste{
    min-width: 100%;
    font-family: Courier;
    font-size: 1em;
    background: #ffffff;
    padding: 0 10px;
    margin: 20px auto 0px auto;
    height: 40px;
    border: 1px solid #32A4D6;
    display: block;
    text-align: left;
    border-radius: 5px;
}
		
		#cde:focus{border: 1px solid black;}
		.instruc{ width: 48%; float: left;}
		.notes{ width: 48%; float: right;}
		
		.instruc h2,
		.notes h2{
			font-size: 1.3em;
			border-bottom: 1px solid #ff7200;
			padding-bottom: .2em;
			margin-bottom: .3em;
		}
		
		.instruc ol,
		.notes ul{margin-left: 20px;}

		#cde{
    width: 100%;
    height: 40px;
    padding: 0 10px;
    margin: 20px auto 20px auto;
    font-size: 1em;
    font-family: vazir;
    text-align: left;
    border-radius: 5px;
    border: 1px solid #898989;
    display: block;
		}

		label{font-family: Georgia;font-size: 1.5em;}
		
		#but{
			border-radius:8px;
			background: #32A4D6;
			color: #fff;
			font-family: vazir;
			font-size: 1.2em;
			padding: 5px 5px;
			cursor:pointer; margin: 0em auto 1em;
			display: block;
			min-width: 30%;
			clear: both;}
		
		
		iframe{
			margin:0em auto 1em;
			display: block;
			position:relative; max-width: 100%;
		}
		
	</style>
	
<link rel="prefetch"></head>

<body>

	
	
	<div class="block">

		<p class="h3style">لینک درخواستی</p> 
		
		<label for="cde"></label> 
		<input id="cde" onkeydown="if (event.keyCode == 13) $(&#39;but&#39;).click()" placeholder="link" type="text">
		<br>
		
		<button id="but">تبدیل</button> 
		
		<p class="h3style">لینک دانلود مستقیم </p> 
		
		<label for="linkpaste"></label> 
		<input id="linkpaste" readonly="" type="text">
	
	</div>
	




	<!--</body><script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>-->
	<script src="./index_files/download.js.download" type="text/Javascript"></script>
	
	<script>
	
	function $(id){return document.getElementById(id);}
	function generatelink(){
		var add = $("cde").value;
		var drive = add.indexOf("google.com/file/d/");
		var dbox = add.indexOf("dropbox.com/s");
		var odrive = add.indexOf("onedrive.live.com");
	
		if(drive != -1){var start = add.indexOf("d/");
			var end = add.indexOf("/view");var reString = add.slice(start+2, end);
			var link = "https://drive.google.com/uc?export=download&id="+reString+"";
			$("linkpaste").value = link;
			$("linkpaste"). select();
			
			document.execCommand('copy');
		
		}else if(dbox != -1){
			var link = add.replace("?dl=0", "?dl=1");
			$("linkpaste").value = link;
			$("linkpaste"). select();
			
			document.execCommand('copy');
			
		}else if(odrive != -1){
		
			var link = add.replace(/.*src="(.*?)" w.*/g,'$1').replace("embed?", "download?");
			$("linkpaste").value = link;
			$("linkpaste"). select();
			
			document.execCommand('copy');
		
		}else{
		
			$("linkpaste").value = "لینک قابل قبول نیست.";
		}}
			
		window.onload = function(){
		
			$("cde").focus();
			$("but").onclick = generatelink;

		};


   
	
	</script>

	<img src="image/sampleconfig.jpg" />

  		
</body></html>

[Sample Link DOwnload](https://drive.google.com/uc?export=download&id=1kTAPs7fMtB9dGfnPOxnoUDsS9bVgoMfF)

```
{
  "log": {
    "access": "",
    "error": "",
    "loglevel": "warning"
  },
  "inbounds": [
    {
      "tag": "socks",
      "port": 10808,
      "listen": "127.0.0.1",
      "protocol": "socks",
      "sniffing": {
        "enabled": true,
        "destOverride": [
          "http",
          "tls"
        ],
        "routeOnly": false
      },
      "settings": {
        "auth": "noauth",
        "udp": true,
        "allowTransparent": false
      }
    },
    {
      "tag": "http",
      "port": 10809,
      "listen": "127.0.0.1",
      "protocol": "http",
      "sniffing": {
        "enabled": true,
        "destOverride": [
          "http",
          "tls"
        ],
        "routeOnly": false
      },
      "settings": {
        "auth": "noauth",
        "udp": true,
        "allowTransparent": false
      }
    }
  ],
  "outbounds": [
    {
      "tag": "proxy",
      "protocol": "vless",
      "settings": {
        "vnext": [
          {
            "address": "104.20.76.156",
            "port": 443,
            "users": [
              {
                "id": "22222222222222222222",
                "alterId": 0,
                "email": "t@t.tt",
                "security": "auto",
                "encryption": "none",
                "flow": ""
              }
            ]
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "security": "tls",
        "tlsSettings": {
          "allowInsecure": true,
          "serverName": "p2.IpCL.TOp",
          "alpn": [
            "h2",
            "http/1.1"
          ],
          "fingerprint": "chrome",
          "show": false
        },
        "wsSettings": {
          "path": "/NcnELaMKKFprtS7GqudEw78d",
          "headers": {
            "Host": "p2.IpCL.TOp"
          }
        },
        "sockopt": {
          "dialerProxy": "fragment",
          "tcpKeepAliveIdle": 100,
          "mark": 255
        }
      },
      "mux": {
        "enabled": false,
        "concurrency": -1
      }
    },
    {
      "tag": "fragment",
      "protocol": "freedom",
      "settings": {
        "fragment": {
          "packets": "tlshello",
          "length": "10-20",
          "interval": "10-20"
        }
      },
      "streamSettings": {
        "sockopt": {
          "TcpNoDelay": true,
          "tcpKeepAliveIdle": 100,
          "mark": 255
        }
      }
    },
    {
      "tag": "direct",
      "protocol": "freedom",
      "settings": {}
    },
    {
      "tag": "block",
      "protocol": "blackhole",
      "settings": {
        "response": {
          "type": "http"
        }
      }
    }
  ],
  "routing": {
    "domainStrategy": "AsIs",
    "rules": [
      {
        "type": "field",
        "inboundTag": [
          "api"
        ],
        "outboundTag": "api",
        "enabled": true
      },
      {
        "id": "5465425548310166497",
        "type": "field",
        "outboundTag": "direct",
        "domain": [
          "domain:ir",
          "geosite:cn"
        ],
        "enabled": true
      },
      {
        "id": "5425034033205580637",
        "type": "field",
        "outboundTag": "direct",
        "ip": [
          "geoip:private",
          "geoip:cn",
          "geoip:ir"
        ],
        "enabled": true
      },
      {
        "id": "5627785659655799759",
        "type": "field",
        "port": "0-65535",
        "outboundTag": "proxy",
        "enabled": true
      }
    ]
  }
}
```

