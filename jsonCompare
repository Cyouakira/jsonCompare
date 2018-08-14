#coding=utf-8
import json


class ompareJSON_Utils():
    # ----------------------------------------------------------------------
    def __init__(self):
        """Constructor"""

    def compareJSON(self, content, content1):
        jsonObj = json.loads(content)
        jsonObj1 = json.loads(content1)

        if isinstance(jsonObj, dict):
            rootlist = jsonObj.keys()
            for rootkey in rootlist:
                subvalue = jsonObj[rootkey]
                if rootkey in jsonObj1:
                    subvalue1 = jsonObj1[rootkey]
                    if isinstance(subvalue, (tuple, list, dict)):
                        for i in range(len(subvalue)):
                            self.compareJSON(json.dumps(subvalue[i]), json.dumps(subvalue1[i]));
                    else:
                        if subvalue != subvalue1:
                            raise Exception(rootkey + "的value值不同")
                else:
                    raise Exception("对比数据中没有这个key." + rootkey)

        #如果是jsonArray的话对比
        if isinstance(jsonObj, (tuple, list)):
            for i in range(len(jsonObj)):
                self.compareJSON(json.dumps(jsonObj[i]), json.dumps(jsonObj1[i]));



if __name__ == '__main__':
    ompareJSON_Utils().compareJSON("""[{"test":"testvalue"}]""", """[{"test":"testvalue"}]""")
