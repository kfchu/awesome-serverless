## Platforms (Hosted)

- [AWS Lambda](https://aws.amazon.com/lambda) - Run code without thinking about servers. Pay only for the compute time you consume.
- [Azure Functions](https://azure.microsoft.com/en-us/services/functions/) - Accelerate your development with an event-driven, serverless compute experience. Scale on demand and pay only for the resources you consume.
- [Google Cloud Functions](https://cloud.google.com/functions/docs/) - Event-driven serverless compute platform
- [IBM Cloud Functiuons](https://console.bluemix.net/openwhisk) - IBM Cloud Functions (基于 Apache OpenWhisk）是函数即服务 (FaaS) 平台，可执行函数以响应传入事件，并且在不使用时不会产生任何开销
- [阿里云函数计算](https://help.aliyun.com/product/50980.html?spm=a2c4g.11186623.6.539.2f8b29e9IFTorg) - 阿里云函数计算是事件驱动的全托管计算服务。[触发器列表](https://help.aliyun.com/document_detail/74707.html?spm=a2c4g.11186623.6.570.38ea68a0KROFyX)
- [华为云函数服务FunctionStage](https://www.huaweicloud.com/product/functionstage.html) - 函数服务（FunctionStage）是一项基于事件驱动的函数托管计算服务。原函数服务FunctionStage和原函数工作流FunctionGraph两个服务已合并成一个新的服务即函数工作流FunctionGraph。[触发器列表](https://support.huaweicloud.com/usermanual-functiongraph/functiongraph_01_0160.html)
- [腾讯云无服务器云函数SCF](https://cloud.tencent.com/product/scf) - 安全稳定、管理简化、易用且高效的低成本无服务器函数计算平台。[触发器列表](https://cloud.tencent.com/document/product/583/9705)

各大厂商的横向对比推荐阅读[Serverless/FaaS的现状和未来](http://jolestar.com/serverless-faas-current-status-and-future/)

## Platforms (Installable)

- [Knative](https://github.com/knative) - 谷歌开源的 serverless 架构方案，旨在提供一套简单易用的 serverless 方案，把 serverless 标准化（CNCF Standard）。Google Cloud Next '18 上重点推荐了此项目。四大厂商（Google，Pivotal，IBM，Red Hat）参与了此项目，其中Pivotal和IBM表示自己手中的开源FaaS项目(分别是riff和OpenWhisk)会与Knative进行对接。

  Knative分为3个可插拔的子系统：

  - Build：构建系统，把用户的代码build成镜像
  - Serving：服务系统，请求路由，容器部署和计算、auto scale等功能
  - Eventing：事件系统，事件的绑定和触发

- [OpenWhisk](https://openwhisk.apache.org/) - IBM贡献的开源项目，Apache基金孵化项目之一。同时IBM的Bluemix上提供的serverless服务就使用了OpenWhisk。使用Scala编写，架构基于Akka的actor模型，通过消息队列存放事件（接近Knative的eventing模型），Invoker去调度容器。容器编排可以基于K8S也可以基于Mesos。在减少冷启动方面下了[不少功夫](https://medium.com/openwhisk/squeezing-the-milliseconds-how-to-make-serverless-platforms-blazing-fast-aea0e9951bd0)。

- [fission](https://github.com/fission/fission) - Platform9开源的一个基于K8S的Serverless框架。Go编写，每种语言环境维护一个 Pod 池子，然后调度器把 Function 分配给合适的 Pod 运行。创建 Function 后，需要在Router设置路由，通过 HTTP 触发（当前只有Http一种trigger）。fission的详细架构可以看[这里](https://github.com/fission/fission/blob/master/Documentation/Architecture.md)

- [fn](https://github.com/fnproject/fn) - iron.io/function团队重新思考serverless，然后做了这个fn project（iron.io在2017年被Oracle收购）。fn Out of box 支持Java, Go, Ruby, Python, PHP, and Node.js。

  设计可以看官方的[presentation](https://docs.google.com/presentation/d/1zdgzSgCfhmF_zK-ziMB_-oqG2C2xVlCE90M1aO70SqU/edit#slide=id.g2d4c809d12_0_1)，可以看看iron.io前CEO谈谈[Why we built Fn Project](https://medium.com/fnproject/8-reasons-why-we-built-the-fn-project-bcfe45c5ae63)

- [Kubeless](https://github.com/kubeless/kubeless) - 自觉是最K8s native的（在Knative出来之后这句话可能要改）。至于为什么这么自信，是因为

- [Qinling](https://github.com/openstack/qinling)(秦岭) - Openstack 上的FaaS，[孔令贤](https://lingxiankong.github.io/index.html)是contributor之一。

## Framework

- [Serverless](https://serverless.com/) 名字起得比较general，实际上是一个开发工具，与各大公有云厂商和开源平台做集成，开发者使用此工具开发好function然后无缝部署到不同的平台之中，避免了vendor lock-in的问题。
- [Spring Cloud Function](https://cloud.spring.io/spring-cloud-function/) 使用Spring生态系统构建Java Function, 提供插件支持各大厂商如ASW，Azure，Apache OpenWhisk的插件
- [StdLib](https://github.com/stdlib/lib) - 专注于FaaS微服务，提供类库以及平台。
- Apex - <TODO>
- Shep - <TODO>

## Standards

- [Serverless Cloud Native Landscape](https://github.com/cncf/wg-serverless) - CNCF Serverless全景图
- [Cloud Native Events](https://github.com/cncf/wg-serverless/tree/master/proposals/cloudevents) - 提出一个通用的事件描述和pub/sub协议规范。Knative, fn project follow此规范。
- Docs of Nuclio - CNCF Serverless Workgroup指定规范时用了不少Nuclio的例子，下面是其中2个范例：
  - [Function Configuration](https://github.com/nuclio/nuclio/blob/master/docs/reference/function-configuration/function-configuration-reference.md) 函数的描述
  - [Benchmarking](https://github.com/nuclio/nuclio/blob/master/docs/tasks/benchmarking.md)

## Articles & Blogs

- [Serverless/FaaS的现状和未来](http://jolestar.com/serverless-faas-current-status-and-future/) - 快速了解什么是FaaS/Serverless, 现状，以及适用场景
- [Serverless Architecture](https://martinfowler.com/articles/serverless.html) - 来自martinfowler.com，主要探讨理论，什么是Serverless，什么不是Serverless，与PaaS对比等
- [Apache OpenWhisk @ Medium](https://medium.com/openwhisk) - 不少干货，例如这篇<[Squeezing the milliseconds: How to make serverless platforms blazing fast!](https://medium.com/openwhisk/squeezing-the-milliseconds-how-to-make-serverless-platforms-blazing-fast-aea0e9951bd0)>会谈到如何加速冷启动
- [Snafu: Function-as-a-Service (FaaS) Runtime Design and Implementation](https://arxiv.org/abs/1703.07562) - 苏黎世大学的一篇论文，介绍如何设计一个FaaS平台，在GitHub放了[源码](https://github.com/serviceprototypinglab/snafu)
- [Serverless应用开发指南](http://serverless.ink/) - 介绍如何用Serverless Framework去开发几个serverless 应用，应用在AWS Lambda上部署
- [Serverless Architectures Security Top 10](https://www.puresec.io/blog/serverless-top-10-released) - Puresec的一个关于Servlerless安全报告，列举最具风险的10个安全问题

## Books

- [What is Serverless?](https://www.oreilly.com/programming/free/what-is-serverless.csp)-  O'Reilly出版的Serverless入门小册子，免费。关于Serverless的分类有这么一段描述：“Serverless actually covers a range of techni‐ ques and technologies. We group these ideas into two areas: Back‐ end as a Service (BaaS) and Functions as a Service (FaaS).”
- [Serverless的入门与思考](http://q.infoqstatic.com/ppt/serverlessminibook.pdf) 《架构师》小册子
- [Buildling Serverless Architecture](https://www.amazon.co.uk/Building-Serverless-Architectures-Cagatay-Gurturk/dp/1787129195) - 教你怎么用AWS Lambda，反而Achitecture谈得很少。

## Conferences

- [Serverlessconf](https://www.youtube.com/channel/UCqlcVgk8SkUmve4Kw4xSlgw) 油管
- [Serverlessdays](https://www.youtube.com/channel/UCYzAnR_SebAmLRkKIbK_YoQ) 油管