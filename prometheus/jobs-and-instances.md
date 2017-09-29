# 作业和实例

prometheus 中，将任意一个独立的数据源（target）称之为实例（instance）。包含相同类型的实例的集合称之为作业（job）。 如下是一个含有四个重复实例的作业：

    - job: api-server
        - instance 1: 1.2.3.4:5670
        - instance 2: 1.2.3.4:5671
        - instance 3: 5.6.7.8:5670
        - instance 4: 5.6.7.8:5671

