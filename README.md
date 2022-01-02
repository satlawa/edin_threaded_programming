# Threaded Programming with OpenMP

Implementation and performance analysis of threaded programming shedules in OpenMP.

## Description

This project uses two distinct loops to analyse the performance of the various schedule clauses and the speedup gained by using an ever-increasing number of threads. The two loops have the following workload per loop counter:

<img src="images/loop_1.png" alt="Loop 1" style="height: 200px; width:200px;"/> <img src="images/loop_2.png" alt="Loop 2" style="height: 200px; width:200px;"/>

The left figure shows workload of loop 1, the right figure shows workload of loop 2.

The loops can be inpected in more detail in the program files [`loop_schedules.c`](loops_schedules/loop_schedules.c) and [`loops_affine.c`](loops_affine/loop_affine.c) or in any of the two provided reports [report schedules](report_shedules.pdf) and [report affine](report_affine.pdf).

We investigate the perfomance of the build in schedules 

`auto` | `static` | `static,n` | `dynamic,n` | `guided,n` 

as well as the self implemented schedule 

`affine` 

The implementations can be found in [`loop_schedules`](loops_schedules) and [`loop_affine`](loops_affine) respectively.

All performance runs were conducted on *Cirrus UK National Tier-2 HPC*. The achived speedup of the best perfoming build in schedule and the self implemented affine schedule are shown here:

<img src="images/speedup_loop_1.png" alt="Speedup Loop 1" style="height: 200px; width:200px;"/> <img src="images/speedup_loop_2.png" alt="Speedup Loop 2" style="height: 200px; width:200px;"/>

The left figure shows the comparison of the actual and ideal speedup for loop 1 using the affine schedule and the guided schedule, while the right figure shows the comparison of the actual and ideal speedup for loop 2 using the affine schedule and the dynamic,16 schedule.

The project is described in detail in [report schedules](report_shedules.pdf) and [report affine](report_affine.pdf).


## Requirements

gcc, make


## Make
This project uses [Make](https://www.gnu.org/software/make/). The Makefile has four targets:
* `make` compiles the source code and generates an executable
* `make clean` deletes the executable and object file


## Instructions

1. Clone the project repository: `git clone https://github.com/satlawa/edin_threaded_programming`

2. Change directory into [`loop_schedules`](loops_schedules) or [`loop_affine`](loops_affine): `$ cd loop_schedules`

2. Build the project: `$ make`

3. Run the resulting executable: `$ ./loop_schedules`
