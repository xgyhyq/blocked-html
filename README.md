# blocked-html
一个简单的自定义封锁提示页面
如果不需要显示用户的IP与归属地，去掉如下代码即可：

    `
      <script>
    fetch('https://api.ipify.org?format=json')
        .then(response => response.json())
        .then(data => {
            document.getElementById('ipAddress').innerText = `Your IP Address is: ${data.ip}`;
            return fetch(`http://ip-api.com/json/${data.ip}`)
        })
        .then(response => response.json())
        .then(data => {
            document.getElementById('location').innerText = `Your IP is located in: ${data.country}, ${data.regionName}, ${data.city}`;
        });
    </script>
