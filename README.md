


.loading {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 5;
}
.loader {
    left: 50%;
    margin-left: -4em;
    font-size: 10px;
    border: 0.8em solid rgba(218, 219, 223, 1);
    border-left: 0.8em solid #ee7f00;
    animation: spin 1.2s infinite linear;
    z-index: 5;
}
.loader,
.loader:after {
    border-radius: 50%;
    width: 8em;
    height: 8em;
    display: block;
    position: absolute;
    top: 50%;
    margin-top: -4.05em;
    z-index: 5;
}

@keyframes spin {
    0% {
        transform: rotate(360deg);
    }
    100% {
        transform: rotate(0deg);
    }
}


-----------------------------<div *ngIf="loading" class="loading" style="z-index: 999999">
        <div class="loader"></div>
    </div>
