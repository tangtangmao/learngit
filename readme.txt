
API�Զ�������
�ſ�
����Ŀ��pytest��assertpy��requests��PyMySQL��allure���
pytest��python��һ����Ԫ���Կ��,https://docs.pytest.org/en/latest/
assertpy��һ�������ḻ�Ķ��Կ⣬֧��pytest,https://github.com/ActivisionGameScience/assertpy
requests��http������,http://docs.python-requests.org/en/master/
PyMySQL���ڲ���MySQL���ݿ�,https://github.com/PyMySQL/PyMySQL
allure�������ɲ��Ա���,http://allure.qatools.ru/
ʹ��
һ������׼��
1����װpython����ģ��
pip install -r requirements.txt
2����װallure
Դ��װ
sudo apt-add-repository ppa:qameta/allure
sudo apt-get update
sudo apt-get install allure
������װ��ʽ��https://github.com/allure-framework/allure2
�ֶ���װ
����2.4.1�汾:https://github.com/allure-framework/allure2/releases
��ѹallure-2.4.1.zip
����ϵͳ��������:export PATH=/home/john/allure-2.4.1/bin:$PATH
3����װopenjdk8
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt-get update
sudo apt-get install openjdk-8-jdk
�����޸�����
vim config/init.ini ������Ҫ��ʼ������Ŀ
vim config/projectName.ini ���ò�����Ŀ����Ϣ
�������в���
cd APIAutomationTest/
python runTest.py --help
python runTest.py ����casesĿ¼���е�����
python runTest.py -k keyword ����ƥ��ؼ��ֵ���������ƥ���ļ�����������������
python runTest.py -d dir ����ָ��Ŀ¼��������Ĭ������casesĿ¼
�ġ����ɲ��Ա���
cd APIAutomationTest/
python generateReport.py -p 9080
���ʵ�ַhttp://ip:9080
��ʹ��Ubuntu���б�������ʱ������ʹ��sudoȨ�ޣ������޷����ɣ�allure��֧��
��Ŀ�ṹ
base ����������
cases ��������Ŀ¼
common ����ģ��
config�������ļ�
init ��ʼ��
logs ��־Ŀ¼
output ���Խ�����Ŀ¼
pojo ����Զ��������
test_data ��������Ĳ�������Ŀ¼
runTest.py �������нű�
generateReport.py �������ɽű�
����淶
ͳһʹ��python 2.7
����ʹ��-*- coding:utf8 -*-,�Ҳ�ָ��������
��/������ע�;�д��class/def��һ�У�����������˫������ʽע��
�ֲ�����ע��ʹ��#��
���еĲ���ģ���ļ�����test_projectName_moduleName.py����
���еĲ����඼��Test��ͷ�����з���(����)����test_��ͷ
ÿ��������Ŀ����casesĿ¼�ﴴ��һ��Ŀ¼����Ŀ¼��������api��scenrarios����Ŀ¼
case��Ӧsetup/teardown��fixtureͳһ������fixture_[test_case_method_name]
pytest����
@pytest.mark.skip(reason='�ù����ѷ���')
@pytest.mark.parametrize('key1,key2',[(key1_value1,key2_value2),(key1_value2,key2_value2)])
@pytest.mark.usefixture('func_name')
ע���
����pytestʱָ����Ŀ¼��Ӧ����conftest.py������������ģ����ʹ�á�@allure.step��Ӱ��fixture�����ڽű��в�ʹ��@allure.step