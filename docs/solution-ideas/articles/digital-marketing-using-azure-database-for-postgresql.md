---
title: Digital Campaign Management
titleSuffix: Azure Solution Ideas
author: adamboeglin
ms.date: 12/16/2019
description: Engage with customers around the world with rich, personalized digital marketing experiences. Quickly build and launch digital campaigns that automatically scale based on customer demand.
ms.custom: acom-architecture, postgresql, use cases, azure, solutions, web-apps, 'https://azure.microsoft.com/solutions/architecture/digital-marketing-using-azure-database-for-postgresql/'
ms.service: architecture-center
ms.subservice: solution-idea
---

# Digital Campaign Management

[!INCLUDE [header_file](../header.md)]

Engage with customers around the world with rich, personalized digital marketing experiences. Quickly build and launch digital campaigns that automatically scale based on customer demand.

## Architecture

<!-- markdownlint-disable MD033 -->
<!-- cSpell:ignore viewbox segoe semibold dasharray linecap miterlimit tspan evenodd -->

<svg class="architecture-diagram" aria-labelledby="digital-marketing-using-azure-database-for-postgresql" height="434" viewbox="0 0 626.343 434"  xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <g style="isolation:isolate">
        <text fill="#5b5b5b" font-family="SegoeUI, Segoe UI" font-size="14" transform="translate(3.797 73.785)">
            B<tspan letter-spacing="-.013em" x="8.025" y="0">r</tspan><tspan x="12.708" y="0">owser</tspan>
        </text>
        <path fill="none" stroke="#969696" stroke-miterlimit="10" stroke-width="1.5" d="M68.275 27.03h309.068v101.435"/>
        <path fill="#969696" d="M372.107 126.933l5.236 9.067 5.235-9.067h-10.471z"/>
        <path d="M0 47.653A2.354 2.354 0 002.347 50h53.991a2.354 2.354 0 002.347-2.347V10.915H0z" fill="#59b4d9"/>
        <path d="M56.338 0H2.347A2.354 2.354 0 000 2.347v8.92h58.685v-8.92A2.354 2.354 0 0056.338 0" fill="#a0a1a2"/>
        <path d="M2.347 0A2.354 2.354 0 000 2.347v45.306A2.354 2.354 0 002.347 50H4.93L51.174 0z" fill="#fff" opacity=".2" style="isolation:isolate"/>
        <path fill="#fff" d="M17.305 3.181h38.371v4.514H17.305z"/>
        <circle cx="7.9" cy="5.814" fill="#3999c6" r="2.633"/>
        <path d="M573.663 158.933v-.409c0-10.5-9-19.235-20.053-19.371-.273-.409-6.548.136-6.548.136-9.959 1.228-17.734 9.549-17.734 19.235 0 .273-1.091 7.912 6.684 14.324 3.547 3.138 7.23 11.6 7.776 14.051l.409.819h14.46l.409-.819c.546-2.456 4.365-10.913 7.776-13.915 7.776-6.548 6.821-13.778 6.821-14.051z" fill="#68217a"/>
        <path fill="#7a7a7a" d="M544.469 192.628h14.46v4.638h-14.46zM548.971 207.088h5.32l4.502-4.774h-14.324l4.502 4.774z"/>
        <path d="M555.246 187.035h-2.728V169.71H550.2v17.19h-2.73v-17.19h-2.319a5.125 5.125 0 01-5.047-5.047 5.047 5.047 0 0110.095 0v2.319h2.319v-2.319a5.047 5.047 0 115.047 5.047h-2.319zm-10.095-24.692a2.3 2.3 0 00-2.319 2.319 2.391 2.391 0 002.319 2.319h2.319v-2.319a2.493 2.493 0 00-2.319-2.319zm12.414 0a2.391 2.391 0 00-2.319 2.319v2.319h2.319a2.391 2.391 0 002.319-2.319 2.3 2.3 0 00-2.319-2.319z" fill="#fff" opacity=".65"/>
        <path d="M553.609 139.152c-.273-.409-6.548.136-6.548.136-9.959 1.228-17.734 9.549-17.734 19.235 0 .273-.955 6.957 5.32 13.1l29.466-29.466a20.035 20.035 0 00-10.504-3.005z" fill="#fff" opacity=".15"/>
        <path d="M388.536 200.839a24.995 24.995 0 114.656-35.03 24.9 24.9 0 01-4.656 35.03" fill="#59b4d9"/>
        <path d="M383.943 185.378a5.385 5.385 0 007.541 1c.123-.094.218-.208.33-.309 2.409 1.7 4.082 2.817 5.025 3.459a21.566 21.566 0 00.67-2.142c-1-.741-2.343-1.778-4.29-3.356a5.34 5.34 0 00-7.666-6.548 222.638 222.638 0 01-8.293-7.833c9.165-4.929 15.676-4.207 15.676-4.207a25.109 25.109 0 00-3.606-3.7 26.627 26.627 0 00-16.729 3.119q-3.429-3.589-6.983-7.712a23.264 23.264 0 00-3.318 1.351 53.84 53.84 0 006.754 8.565l.017.017a46.293 46.293 0 00-6.944 6.015c-.29.309-.569.62-.842.931a7.546 7.546 0 00-4.117.282 18.265 18.265 0 01-1.724-10.832 26.353 26.353 0 00-2.692 3.267 16.016 16.016 0 00.985 10.1 7.538 7.538 0 00-.005 9.153 7.743 7.743 0 00.559.645 37.87 37.87 0 00-1.46 8.761c.237.322.237.582.472.9a25.375 25.375 0 004.16 4.008 27.556 27.556 0 011.714-11.372 7.507 7.507 0 003.483-.566c.64.563 1.31 1.132 2.025 1.711a41.672 41.672 0 007.285 4.643 4.941 4.941 0 007.951 4.437 4.918 4.918 0 001.108-1.216 44.6 44.6 0 009.806 1.019c.386 0 2.177-2.436 3.2-3.946a26.373 26.373 0 01-12.3-.84 4.913 4.913 0 00-7.516-3.113 46.853 46.853 0 01-6.758-4.49q-.707-.559-1.359-1.118a7.578 7.578 0 00.318-7.55c.286-.286.567-.573.871-.857a54.887 54.887 0 016.519-5.274c-.082-.076-.156-.156-.236-.233.081.075.157.152.239.227 3.121 2.886 6.43 5.621 9.564 8.065a5.348 5.348 0 00.566 5.539z" fill="#fff"/>
        <text fill="#5b5b5b" font-family="SegoeUI, Segoe UI" font-size="14" transform="translate(184.397 234.285)">
            CDN
        </text>
        <text fill="#5b5b5b" font-family="SegoeUI, Segoe UI" font-size="14" transform="translate(315.829 234.285)">
            CMS on <tspan letter-spacing="-.024em" x="52.473" y="0">W</tspan><tspan x="65.215" y="0">eb App</tspan>
        </text>
        <text fill="#5b5b5b" font-family="SegoeUI, Segoe UI" font-size="14" transform="translate(480.981 234.285)">
            Application Insights
        </text>
        <path d="M210.161 179.182h-37.313a2.814 2.814 0 01-2.805-2.805 2.814 2.814 0 012.805-2.805h37.313a2.814 2.814 0 012.805 2.805 2.814 2.814 0 01-2.805 2.805zM202.586 202.608h-34.505a2.814 2.814 0 01-2.805-2.805 2.814 2.814 0 012.805-2.803h34.505a2.814 2.814 0 012.805 2.805 2.814 2.814 0 01-2.805 2.803zM198.519 191.245h-34.508a2.814 2.814 0 01-2.806-2.805 2.814 2.814 0 012.805-2.805h34.505a2.814 2.814 0 012.805 2.805 2.814 2.814 0 01-2.801 2.805z" fill="#7a7a7a"/>
        <path d="M231.342 196.576a5.958 5.958 0 00-5.883-6.032h-.849a19.087 19.087 0 00.559-4.208 15.775 15.775 0 00-15.709-15.711 15.964 15.964 0 00-14.869 10.661 14.1 14.1 0 00-3.507-.561 10.945 10.945 0 000 21.883h34.648a6.2 6.2 0 005.611-6.032" fill="#3999c6"/>
        <path d="M196.695 202.467a9.99 9.99 0 01-2.945-5.33 10.543 10.543 0 0111.642-13.046 15.274 15.274 0 018.837-12.625 17.9 17.9 0 00-4.769-.841 15.964 15.964 0 00-14.869 10.661 14.1 14.1 0 00-3.507-.561 10.945 10.945 0 000 21.883z" fill="#fff" opacity=".2" style="isolation:isolate"/>
        <path fill="none" stroke="#969696" stroke-miterlimit="10" stroke-width="1.5" d="M200.343 27v103.465"/>
        <path fill="#969696" d="M195.107 128.933l5.236 9.067 5.235-9.067h-10.471z"/>
        <path fill="none" stroke="#969696" stroke-miterlimit="10" stroke-width="1.5" d="M502.54 182.03h-73.73"/>
        <path fill="#969696" d="M501.008 176.794l9.067 5.236-9.067 5.235v-10.471zM430.342 176.794l-9.067 5.236 9.067 5.235v-10.471z"/>
        <image height="151" opacity=".25" style="mix-blend-mode:multiply" transform="translate(293.343 283)" width="333" xlink:href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAU0AAACXCAYAAACRIgk5AAAACXBIWXMAAAsSAAALEgHS3X78AAAFcElEQVR4Xu3ZsWpUWxTH4WOiiBgEGxGJlVYWdhYS9RW0FruA3gfwGVKnUZ/CF7AatPEN7BSt7AQtBMWbu/45Z7zGTC4uuNXJN/AVM5yzp/ux9t7D3t7esEp9TgAcV0e28YhYrk3Wy0mAYyTdWzbwUDxXTZZ54VQ5Xc6Us5MNgBlbti7dS//SwfTwwOT5ezTXp4ezwPlyoVwqm5PLADO0bFx6l+6lf+lgergfzgPRHA4G81y5WK6U6+VGuVm2yi2AGUrf0rn0Lt1L/9LB9PBAOJfRzN49o+jG9OC1crvcLQ/KdnlYHpW/AGYkXUvf0rn0Lt1L/9LB9DBdTB/Xpl7+vPhJTTOSXi13yv3yuOyU3fKkPAOYofQtnUvv0r30Lx1MD9PF9HH/YmgY/t2a5/Aze/mMpvemF7PQ8/KiLMrL8gpgRtK1xTB2Lr1L99K/dDA9TBfTx/Xhl2jmmj23RjkEzZ4+I+rOtMDr8qa8K+/LB4AZSdfSt3QuvUv30r90MD1MF9PHdPJQNDeH8TB0exhH1RfTQh/Lp/K5fAGYkXQtfUvn0rt0L/1LB9PDdHFlNHPYmav33CLlUDQj6qK8nRb8Wr6V7wAzkq6lb+lcercYxv6lg1vD2MX08cho5vo9N0pPh3Gvn9H187Twj/I3wIyka+lbOpfepXvpXzqYHv5xNHOjlEPS7Pkzwn6f/mAPYEbStfQtnUvv0r30TzQBVhBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2ABtEEaBBNgAbRBGgQTYAG0QRoEE2Ahv8tmk/Ly/K+fC7fyo/pDwDmIl1L39K59C7dS//+OJpb5WF5UhblbflUvk4LfweYkXQtfUvn0rvFMPYvHdwa/iOaZ8tmuVm2y255Ud6Uj9OCKfEXgBlJ19K3dC69S/fSv3QwPUwX08eV0bxUbpQHZac8L6+nhd4N4+j6AWBG0rX0LZ1L79K99C8dTA/TxUPRXC9nyoVyvdwrj4dxRM0CKe9iGPf6rwBmJF1bDGPn0rt0L/1LB9PDdDF9XB9+ieZaOV3Ol6vlTrk/vZji7k4LPQOYofQtnUvv0r30Lx1MD9PF9DGdPDHs7eXGff/LqWE87LxYrpXb5e4wjqjbw3go+mgYb5QA5iJdS9/SufQu3Uv/0sH0MF1MH9f2ezlFc7lFT03PTQ9eGcbRNHv6HIbmFukWwAylb+lcepfupX/pYHqYLu5vzX9Gc0U4U9aMpNnL5xB0c3IZYIaWjUvv0r30Lx08EMxV0VyG89T0cA4/z042AGZs2bp0L/1LB5eXP4ej+Vs81yZ54STAMZLuLRt44lAjf/9hxeQJcOwc1cZ/AGZ3ZihaEBNmAAAAAElFTkSuQmCC"/>
        <path fill="#f4f4f4" d="M297.875 287.898h320.468v138.4H297.875z"/>
        <text fill="#5b5b5b" font-family="SegoeUI, Segoe UI" font-size="14" transform="translate(320.778 394.285)">
            Azu<tspan letter-spacing="-.013em" x="23.283" y="0">r</tspan><tspan x="27.966" y="0">e Data</tspan><tspan letter-spacing="-.013em" x="67.929" y="0">b</tspan><tspan x="75.975" y="0">ase </tspan><tspan x="3.989" y="16.8">for </tspan><tspan letter-spacing="-.037em" x="25.276" y="16.8">P</tspan><tspan x="32.597" y="16.8">os</tspan><tspan letter-spacing="-.008em" x="46.741" y="16.8">t</tspan><tspan x="51.375" y="16.8">g</tspan><tspan letter-spacing="-.013em" x="59.62" y="16.8">r</tspan><tspan x="64.302" y="16.8">eSQL</tspan>
        </text>
        <text fill="#5b5b5b" font-family="SegoeUI, Segoe UI" font-size="14" transform="translate(505.767 395.285)">
            <tspan letter-spacing="-.028em">R</tspan><tspan x="7.984" y="0">edis Cache</tspan>
        </text>
        <path d="M515.227 325.7v40.858c0 4.3 9.507 7.7 21.164 7.7V325.7z" fill="#3999c6"/>
        <path d="M536.165 374.25h.34c11.771 0 21.164-3.4 21.164-7.7V325.7h-21.5z" fill="#59b4d9"/>
        <path d="M557.669 325.7c0 4.188-9.507 7.7-21.164 7.7s-21.278-3.509-21.278-7.7 9.507-7.7 21.164-7.7 21.278 3.509 21.278 7.7" fill="#fff"/>
        <path d="M553.368 325.243c0 2.829-7.583 5.093-16.864 5.093s-16.977-2.264-16.977-5.093 7.583-5.093 16.864-5.093 16.977 2.264 16.977 5.093" fill="#7fba00"/>
        <path d="M549.747 328.3c2.264-.905 3.509-1.924 3.509-3.056 0-2.829-7.583-5.093-16.864-5.093s-16.864 2.264-16.864 5.093c0 1.132 1.358 2.264 3.509 3.056 3.056-1.245 7.923-1.924 13.355-1.924a41.256 41.256 0 0113.355 1.924" fill="#b8d432"/>
        <path d="M542.164 341.881v27.276c0 2.829 6.338 5.093 14.147 5.093v-32.369z" fill="#0072c6"/>
        <path d="M556.085 374.25h.226c7.809 0 14.147-2.264 14.147-5.093v-27.276h-14.373z" fill="#0072c6"/>
        <path d="M556.085 374.25h.226c7.809 0 14.147-2.264 14.147-5.093v-27.276h-14.373z" fill="#fff" opacity=".15" style="isolation:isolate"/>
        <path d="M570.458 341.881c0 2.829-6.338 5.093-14.147 5.093s-14.147-2.264-14.147-5.093 6.338-5.093 14.147-5.093 14.147 2.264 14.147 5.093" fill="#fff"/>
        <path d="M567.516 341.541c0 1.811-5.093 3.4-11.2 3.4s-11.2-1.471-11.2-3.4c0-1.811 5.093-3.4 11.2-3.4s11.2 1.585 11.2 3.4" fill="#7fba00"/>
        <path d="M565.139 343.578c1.471-.566 2.377-1.245 2.377-2.037 0-1.811-5.093-3.4-11.2-3.4-6.225 0-11.2 1.471-11.2 3.4 0 .792.905 1.471 2.377 2.037a29.365 29.365 0 0117.656 0" fill="#b8d432"/>
        <path fill="#fff" d="M564.007 358.405l-15.732 13.016 6.112-10.073h-5.319l15.731-12.903-6.111 9.96h5.319z"/>
        <path fill="none" stroke="#969696" stroke-miterlimit="10" stroke-width="1.5" d="M372.166 295.395V245.13"/>
        <path fill="#969696" d="M377.402 293.863l-5.236 9.067-5.235-9.067h10.471z"/>
        <path d="M349.665 322.418v41.411c0 4.359 9.738 7.8 21.678 7.8v-49.211z" fill="#3998c5"/>
        <path d="M371.343 371.48h.34c11.867 0 21.338-3.431 21.338-7.777v-41.285h-21.678z" fill="#59b3d8"/>
        <path d="M392.682 322.8c0 4.246-9.636 7.8-21.451 7.8s-21.566-3.556-21.566-7.8 9.636-7.8 21.451-7.8 21.566 3.556 21.566 7.8" fill="#fff"/>
        <path d="M388.318 322.341c0 2.868-7.685 5.162-17.092 5.162s-17.2-2.293-17.2-5.162 7.685-5.162 17.092-5.162 17.2 2.294 17.2 5.162" fill="#7fb900"/>
        <path d="M384.651 325.438c2.294-.912 3.556-1.95 3.556-3.1 0-2.868-7.685-5.162-17.092-5.162s-17.092 2.294-17.092 5.162c0 1.147 1.376 2.294 3.556 3.1 3.1-1.262 8.029-1.95 13.536-1.95a41.81 41.81 0 0113.536 1.95" fill="#b7d332"/>
        <path d="M383.261 353.559c-3.414.7-3.649-.456-3.649-.456 3.6-5.349 5.112-12.138 3.811-13.8-3.547-4.532-9.692-2.389-9.79-2.333l-.033.006a12.176 12.176 0 00-2.28-.237 5.628 5.628 0 00-3.605 1.079s-10.955-4.513-10.446 5.674c.114 2.166 3.107 16.4 6.683 12.1 1.307-1.572 2.57-2.9 2.57-2.9a3.316 3.316 0 002.166.553l.062-.051a2.387 2.387 0 00.025.613c-.921 1.026-.651 1.21-2.493 1.589-1.863.384-.767 1.067-.055 1.246a3.786 3.786 0 004.226-1.368l-.055.217a6.157 6.157 0 01.57 3.326 9.172 9.172 0 00.213 3.206c.284.773.57 2.514 2.989 2a3.571 3.571 0 003.217-3.431c.1-1.331.342-1.14.352-2.326l.188-.563c.217-1.806.034-2.389 1.279-2.117l.3.026a6.9 6.9 0 002.823-.475c1.518-.7 2.417-1.88.921-1.571z" fill="#336790"/>
        <path d="M368.85 344.623a1.453 1.453 0 00-.494-.154 1.058 1.058 0 00-.727.1.265.265 0 00-.114.177c-.032.228.307.657.731.716a.78.78 0 00.1.007.8.8 0 00.723-.464l.011-.04c.02-.071.001-.215-.23-.342zM378.284 344.267a1.356 1.356 0 00-.49-.01c-.355.051-.7.21-.669.42l.006.021a.723.723 0 00.659.423.74.74 0 00.093-.006.864.864 0 00.486-.267.555.555 0 00.184-.371c-.018-.098-.114-.177-.269-.21z" fill="#fff"/>
        <path d="M384.293 353.515c-.164-.5-.883-.353-1.119-.3-2.4.5-3.079.007-3.219-.131a28.037 28.037 0 003.721-8.365c.665-2.66.652-4.771-.029-5.641a7.776 7.776 0 00-6.043-2.987 11.694 11.694 0 00-4.042.539l-.029.007-.046.016-.041.016a9.41 9.41 0 00-2.14-.278 6.073 6.073 0 00-3.619 1.026 15.831 15.831 0 00-3.461-.87 7.157 7.157 0 00-5.116.921c-1.586 1.125-2.322 3.147-2.179 6.007.07 1.349 2.043 12.093 5.141 13.127a1.893 1.893 0 002.1-.835 56.095 56.095 0 012.394-2.7 3.779 3.779 0 001.8.479 1.619 1.619 0 00.015.19 7.245 7.245 0 00-.325.4c-.414.527-.512.651-1.854.928-.544.114-1.268.324-1.279.863s.746.878 1.193.989a4.075 4.075 0 004.154-1.006 27.674 27.674 0 00.4 6.385 2.973 2.973 0 002.855 2.2 4.586 4.586 0 00.953-.108A3.611 3.611 0 00377.8 361c.2-1.14.539-3.912.684-5.307a3.518 3.518 0 001.279.194 7.076 7.076 0 002.686-.506c.851-.407 2.051-1.23 1.844-1.866zm-6.1 1.482c-.059.779-.509 4.531-.743 5.892a3.017 3.017 0 01-2.836 2.872 2.4 2.4 0 01-3.04-1.51q-.033-.1-.058-.2a33.7 33.7 0 01-.331-7.441.3.3 0 00-.032-.139 1.608 1.608 0 00-.058-.285 1.568 1.568 0 00-.77-.933l-.038-.019a1.14 1.14 0 00-.993-.059 8.076 8.076 0 01.409-1.3l.064-.171c.073-.2.161-.391.255-.607.5-1.117 1.19-2.645.441-6.107a2.106 2.106 0 00-2.421-1.735q-.063.01-.125.025a6.209 6.209 0 00-2.408.859 9.229 9.229 0 012.115-5.633 5.223 5.223 0 013.939-1.482 8.125 8.125 0 015.929 2.589 9.613 9.613 0 012.166 3.558c-1.627-.195-2.721.1-3.259.865-1.14 1.637.665 4.881 1.535 6.441.148.266.3.54.35.657a5.764 5.764 0 00.918 1.474 3.114 3.114 0 01.307.424l-.074.021c-.461.124-1.322.366-1.244 1.945zm-15.973.844c-1.02-.336-2.152-2.385-3.188-5.757a36.834 36.834 0 01-1.444-6.588c-.129-2.588.5-4.395 1.882-5.371a5.59 5.59 0 013.257-.876 14.088 14.088 0 014.25.772 2.63 2.63 0 00-.2.18c-2.368 2.39-2.284 6.494-2.28 6.666v.02a19.726 19.726 0 01-.069 3.839 4.221 4.221 0 001.112 3.534 3.679 3.679 0 00.378.336 58.987 58.987 0 00-2.309 2.615c-.48.574-.937.779-1.393.628zm3.423-7a20.524 20.524 0 00.08-3.939 4.8 4.8 0 013.193-1 1.382 1.382 0 011.162 1.209c.7 3.26.092 4.622-.4 5.718-.095.211-.193.429-.274.644l-.064.171a10.027 10.027 0 00-.412 1.265 3.1 3.1 0 01-2.327-.99 3.678 3.678 0 01-.957-3.084zm3.347 5.14a.307.307 0 00.03-.038.523.523 0 01.7-.169l.051.026a.959.959 0 01.416 1.254 3.479 3.479 0 01-3.893 1.254 1.674 1.674 0 01-.729-.358 1.746 1.746 0 01.767-.276c1.5-.307 1.71-.509 2.22-1.154.114-.146.255-.325.445-.536zm9.612-3.093c-.059-.145-.192-.381-.374-.709l-.008-.014c-.745-1.335-2.488-4.462-1.568-5.778a2.085 2.085 0 011.807-.656 7.5 7.5 0 01.987.074 8.153 8.153 0 01-.124 1.31 10.892 10.892 0 00-.148 1.387 10.416 10.416 0 00.114 1.571 5.552 5.552 0 01-.352 3.451 4.186 4.186 0 01-.333-.64zm4.156-5.685a31.493 31.493 0 01-3.267 7.253 4.028 4.028 0 00-.194-.251l-.073-.093-.021-.025a5.827 5.827 0 00.57-4.1 9.9 9.9 0 01-.1-1.467 10.483 10.483 0 01.143-1.316 7.952 7.952 0 00.13-1.6.523.523 0 00.017-.2 9.767 9.767 0 00-5.594-6.4c5.106-1.247 7.754 1.3 8.666 2.456.684.87.583 2.911-.273 5.746zm-3.408 8.438a1.837 1.837 0 00.228-.075 1.544 1.544 0 00.16.122 5.1 5.1 0 003.576.13 1.95 1.95 0 01.328-.043 4.073 4.073 0 01-1.444 1.026 5.6 5.6 0 01-3.561.263c-.062-.036-.075-.063-.076-.07-.064-1.108.371-1.23.8-1.349z" fill="#fff"/>
    </g>
</svg>