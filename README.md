import { waitForAsync, ComponentFixture, TestBed } from '@angular/core/testing';

import { FeederCardComponent } from './feeder-card.component';
import { LocalizationModule } from 'src/app/core/localization/localization.module';
import {  NO_ERRORS_SCHEMA } from '@angular/core';
import { isObject, objectEach } from 'highcharts';
import { type } from 'os';
import { GraphRatioPipe } from 'src/app/shared/pipes/graph-ratio.pipe';

describe('FeederCardComponent', () => {
  let component: FeederCardComponent;
  let fixture: ComponentFixture<FeederCardComponent>;

  beforeEach(waitForAsync(() => {
    TestBed.configureTestingModule({
      imports: [ LocalizationModule ],
      declarations: [ FeederCardComponent ],
      schemas: [NO_ERRORS_SCHEMA]
    })
    .compileComponents();
  }));

  beforeEach(() => {
    fixture = TestBed.createComponent(FeederCardComponent);
    component = fixture.componentInstance;
    fixture.detectChanges();
  });

  it('should create', () => {
    expect(component).toBeTruthy();


  });

  it('should call handleExpandSelectedGrap', () => {

      spyOn(component, 'handleExpandSelectedGrap').and.callThrough();
      const obj = {};
      component.handleExpandSelectedGrap(obj);
      expect(component.handleExpandSelectedGrap).not.toBeUndefined();
    });

  it('should call @input', () => {

  const graph = {};
  fixture.detectChanges();
  component.graph = graph;
  expect(component.graph).toBeUndefined();
  });

  // it('graph name is...', () => {
  //   // tslint:disable-next-line:no-shadowed-variable
  //   const type = {};
  //   fixture.detectChanges();
  //   component.type = type;
  //   expect(component.graph.type).toBe(type);
  // });

});
