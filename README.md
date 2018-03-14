# tui
TUI Javascript Library For UI (TUI前端框架)

# *.tui document For TUI Factory

<root>
    <scripts>
        <script>ui/js/T3.Monitor.js</script>
    </scripts>
    <css>
        <link rel="stylesheet" href="ui/theme/css_home.css" type="text/css" />
    </css>
    <temp id="home">
        <table id="home_ojber">
            <tr>
                <td>TUI_index</td>
                <td id="home_titler"></td>
                <td>
                    <weather id="home_weather"/>
                </td>
            </tr>
        </table>
        <div class="jumppage" onclick="home.jumpEvent('weather')">jump innerPage</div>
        <div class="eventpage" onclick="home.dispatchEvent()">pageEvent</div>
    </temp>
    <code>
        tui.setCache("sessionId", "00004", "faceObj");
        var home = {
            name: "wahah",
            update: function(){
                home_titler.innerHTML += "_update_";
            },
            default: function(){
                home_titler.innerHTML = "H5_Default";
            },
            onPageEvent: function(e){
                home.update();
                alert("event:["+e.type+"] data:["+e.data+"]");
            },
            dispatchEvent: function(event, param){//Look tui(1483)
                alert(event + "i love u");
            },
            jumpEvent: function(param){
                tui.dispatchEvent(Monitor.Event.PageJump, self, param);
            }
        };
        //event Listen
        self.addEventListener(Monitor.Event.PageEvent+"home", home.onPageEvent);
        home.create();
    </code>
</root>
