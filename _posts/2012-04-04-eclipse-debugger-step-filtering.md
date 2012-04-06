---
title: Eclipse Debugger Step Filtering
tags: eclipse
---

Spring proxies calls to methods on other objects. The proxying makes it difficult to step into the method. Previously, I was jumping to the defintion of the method I wanted to step into, setting a breakpoint, continuing execution, and removing the breakpoint. It worked, but was annoying.

Today, I found Eclipse's Step Filtering at Preferences &gt; Java &gt; Debug &gt; Step Filtering. This will skip packages or classes when debugging. I am now filtering the following packages: com.mchange.v2.\*, com.mysql.\*, com.postresql.\*, java.\*, net.sf.cflib.\*, org.apache.\*, org.hibernate.\*, org.postresql.\*, org.slf4j.\*, org.springframework.\*, sun.\*. I left the default java.lang.ClassLoader class filtered as well.

As I debug other areas of my applications, I expect I will tweak these filters. I will try to post updates here.
