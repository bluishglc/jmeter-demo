For more information, please check out this artical from author blog: [JMeter实用案例讲解：生成Mockup/Dummy JSON压测REST API](https://laurence.blog.csdn.net/article/details/108338351)

1. How to Run it?

```bash
nohup /your-jmeter-cli-path/jmeter.sh -n -t /your-jmeter-demo-project-path/demo-testplan.jmx -l result.jtl &
tail -f nohup.out
```
2. Run it with thread and count setting

first, you should change "Demo Thread Group" setting, change the value of `Number of Threads` to `${__P(thread,)}` and the value of `Loop Count` to `${__P(count,)}`,

then assign thread and count via -Jthread and -Jcount, the following is a sample:

```bash
nohup /your-jmeter-cli-path/jmeter.sh -Jthread=2 -Jcount=50 -n -t /your-jmeter-demo-project-path/demo-testplan.jmx -l result.jtl &
tail -f nohup.out
```
