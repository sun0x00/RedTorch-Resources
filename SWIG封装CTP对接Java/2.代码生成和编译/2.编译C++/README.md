## Visual Studio IDE ������Ŀ

+ �½�dll��Ŀ

+ ����JDKĿ¼�е�jni.h jni_md.h ��������Ŀ¼(���� C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\jni.h)�����Բ�����һ��ͨ���ڶ������

+ ���Ƶ���Ŀ·�������޸�cpp��������ͷ�ļ��Ĳ��ҷ�ʽ����`<>`��Ϊ`""`��������˵�һ����һ�����Բ�����

+ ��Ŀ����->��������->C/C++->��������->���п� ѡ�񣺶��̣߳�/MT��

+ ��Ŀ����->��������->����->ƽ̨���߼� �����ʵ����Ҫѡ��,��Ӧ������Ŀ¼Ӧ�в���һ�и��ƺ��JDKͷ�ļ�

+ ��Ŀ����->��������->C/C++->Ԥ����ͷ->Ԥ����ͷ ��ʹ�ñ���ͷ

+ ��Ŀ����->���ù����������Ͻǣ�->ȫ��ΪRelease x64��Ĭ��64λ������

+ (�Ǳ�Ҫ)��Ŀ����->��������->C/C++->Ԥ������->Ԥ����������->�༭ ���µ�һ�м��� _CRT_SECURE_NO_WARNINGS


## iconv.hͷ�ļ���Դ
+ Windows
	������Ŀlibiconv-1.15-for-windows-vs2017-project
+ Linux
	iconv.hͷ�ļ�����libiconv-1.15.tar.gz
	
>�����������𣬵���������һ��,���ͨ��SWIG���ɵ�C++�����ƽ̨�������޸�

## ���㵥����Ľ������
���㵥�������Ҫԭ���Ƿֶΰ�byte�ضϴ��䣬������unicode���ܶ��byte������������;ת��ᶪʧ���ݣ�һ���򵥵Ľ����������Java�л�ԭΪbyte[] ƴ�ӣ�Ȼ����new String ��ʹ�ñ���GB18030(����GBK,GB2312),���������

�����ɵ�CPP������ `CThostFtdcSettlementInfoField_1Content_1get`
���������͸�Ϊ`jbyteArray `
�����������滻Ϊ

    jbyteArray jresult = 0 ;
    CThostFtdcSettlementInfoField *arg1 = (CThostFtdcSettlementInfoField *) 0 ;
    char *result = 0 ;

    (void)jenv;
    (void)jcls;
    (void)jarg1_;
    arg1 = *(CThostFtdcSettlementInfoField **)&jarg1;
    result = (char *) ((arg1)->Content);
    {
    	if (result) {
    		jresult = jenv->NewByteArray( strlen(result));
    		jenv->SetByteArrayRegion(jresult, 0, strlen(result), (jbyte*)result);
    	}
    }
    return jresult;



���ս�����磺

	SWIGEXPORT jbyteArray JNICALL Java_xyz_redtorch_gateway_ctp_x64v6v3v15v_api_jctpv6v3v15x64apiJNI_CThostFtdcSettlementInfoField_1Content_1get(JNIEnv *jenv, jclass jcls, jlong jarg1, jobject jarg1_) {
		jbyteArray jresult = 0;
		CThostFtdcSettlementInfoField *arg1 = (CThostFtdcSettlementInfoField *)0;
		char *result = 0;

		(void)jenv;
		(void)jcls;
		(void)jarg1_;
		arg1 = *(CThostFtdcSettlementInfoField **)&jarg1;
		result = (char *)((arg1)->Content);
		{
			if (result) {
				jresult = jenv->NewByteArray(strlen(result));
				jenv->SetByteArrayRegion(jresult, 0, strlen(result), (jbyte*)result);
			}

		}
		return jresult;
	}

** �벻Ҫֱ�Ӹ����϶κ������룬ע�⺯����һ���� **

�ֶ���`CThostFtdcSettlementInfoField.java`�ļ��еĺ��� `getContent()`�����ķ������͸�Ϊ`byte[]`,������õ�������ķ����ķ�������Ҳ��Ϊ`byte[]`ֱ���޴�Ϊֹ

��java�У���û�з���last���֮ǰ���洢����`byte[]`,���ر��֮��ƴ��Ϊһ����`byte[] `ʹ��`new String(contentBytes,"GB18030")`����ɵõ���ȫ��ȷ�Ľ��㵥

