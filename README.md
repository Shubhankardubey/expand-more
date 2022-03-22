.arrow {
  border: solid black;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 3px;
  cursor: pointer;
}

.notArrow{
    padding: 4px;
}

.right {
  transform: rotate(-45deg);
  -webkit-transform: rotate(-45deg);
}

.down {
  transform: rotate(45deg);
  -webkit-transform: rotate(45deg);
}


---------------------------------------------------------------------------------------------------------------

<div>
  <ng-container *ngFor="let item of items;let i=index"> 
      <p>
        <i [class]="item.isExpand ? item.class : 'notArrow'" (click)="openlevel(i,1)"></i>&nbsp; {{item.text}}
        <ng-container *ngFor="let level1 of item.children;let j=index"> 
          <p style="margin:10px">
            <i [class]="level1.isExpand ? level1.class : 'notArrow'" (click)="openlevel(j,2)"></i>&nbsp; {{level1.text}}   
          </p>
      </ng-container>
      </p>
  </ng-container>
</div>


------------------------------------------------------

openlevel(i,level){
  if(level === 1){
    if(this.items[i]['class'] === "arrow down"){
      this.items[i]['class'] = "arrow right"
      this.items[i]['children'] = []
      return
    }
    this.items[i]['children'] = [
      {
        text:"level1",
        value:"level1",
        isExpand:true,
        class:"arrow right"
      }
    ]
    this.items[i]['class'] = "arrow down"
  }
}
