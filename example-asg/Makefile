include ../Makefile.common
ENV = example

.PHONY: set-default-params
set-default-params:
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/alb/latency/high            VALUE=0.2
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/alb/latency/low             VALUE=0.05
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/alb/requests/high           VALUE=20
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/alb/requests/low            VALUE=5
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/asg/cpu/high                VALUE=75
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/asg/cpu/low                 VALUE=30
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/autoscaling/demand/min      VALUE=0
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/autoscaling/demand/percent  VALUE=0
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/autoscaling/dynamic         VALUE=true
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/autoscaling/enabled         VALUE=false
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/autoscaling/max             VALUE=8
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/autoscaling/min             VALUE=1
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/instance/type1              VALUE=t4g.nano
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/instance/type2              VALUE=t4g.micro
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/instance/type3              VALUE=unused
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/instance/weight1            VALUE=1
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/instance/weight2            VALUE=2
	$(MAKE) --no-print-directory update-parameter    NAME=/example-asg/instance/weight3            VALUE=4
	$(DONE)
