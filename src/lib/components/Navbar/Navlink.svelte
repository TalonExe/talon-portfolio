<script>
    let {title, url} = $props()
</script>

<a class="link-wrapper" href="/{url}">
    <span class="fallback">Index</span>
    <div class="img-wrapper">
        <span class="normal">{title}</span>
        <span class="active">{title}</span>
    </div>
    <div class="shape-wrapper">
        <div class="shape red-fill jelly">
            <svg x="0px" y="0px" viewBox="0 0 108.1 47" enable-background="new 0 0 108.1 47">
                <polygon fill="#FF0000" points="29.5,8.5 150.7,0 108.1,32.7 3.1,47 "/>
            </svg>
        </div>
    <div class="shape cyan-fill jelly">
        <svg x="0px" y="0px" viewBox="0 0 108.1 47" enable-background="new 0 0 108.1 47">
            <polygon fill="#00FFFF" points="0.3,17 125.1,0 68.8,45.6 24.3,39 "/>
        </svg>
    </div>
    </div>
</a>