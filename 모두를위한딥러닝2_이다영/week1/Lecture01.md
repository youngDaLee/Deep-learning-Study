Doker Instruction
===
## Doker��?
#### Container-based virtualization System
�����̳� ����� ����ȭ �ý���
- Virtualizetion(����ȭ) : ���ǿ� �������� ���� ���� ��ġ �ִ� �� ó�� ���̰� �� �ִ� ���.
    - �� ��ǻ�Ϳ� �����δ� �ϵ��ũ 1���ε� partition�� ���� C����̺�� D����̺� 2 ���� �ִ� �� ó�� ���̰�
    - ��ǻ�� �ȿ� ������ ��ǻ��(virtual box �̿��� ������ �ȿ� ������, ������ �ȿ� ������)
    - Ŭ���� ������ �ٽɱ��. ������ �ɰ��� ������ �����ϰ�.
        - ��ǻ�� �ϳ��� �ü�� ���� �� �Ѳ����� ������ ���� ġ���� ������.
        - ���� ���� ���� �ֵ� ��� �������ε�.. �ϳ��� ��ġ�� ����� �ٷ� **DOKER** 

- pythorch�� tensorflow ��ġ�� �ʿ� ���� doker ��ġ�ϸ� ok. ���� tensorflow ��ġ������ doker ��ġ �� �ʿ� ����.    



Lecture 01
====
What is ML(Machine Learning)?
---
�ӽŷ����̶�?
- explicit programming : �̷� ȯ�濡�� �̷��� �����ض� �ϰ� �̹� ���α׷��� ����� ���� ��.    
� ��쿡���� explicit �ϰ� ���� �� �� ����
 - Spam filter : ����� ���� �ʹ� ������
 - Automatic driving : ���������� ����� ���� �ʹ� ����

�̸� �����ϱ� ���� �����ڰ� ������ ��� �� ���� ������ ���� **���α׷��� �н��ϰ�** �ɷ��� ���� ���α׷��� �ӽŷ����̶� �Ѵ�. -by. Arthur Samuel

What is learning?
---
�н��� �ϱ� ���� � �����͸� �̸� �־����� ��.
> ### SuperVised learning
������ �ִ� ������(���̺���� �����Ǿ� �ִ� ����Ÿ)-training set-�� ���� �н��� �ϴ� ��
- �갡 ������ϱ� ���ϱ�? ���ߴ� ���α׷�.
 - ������� ����� �̹����� �ش�.
 - �� ����� ������ ���� �н��� �Ѵ�.(�̹� ����� label�� �ִ� ����)    

#### �Ϲ����� ������ ML
- Imane labeling
- Email spam filter : �갡 ���Ը����ΰ�?
- Predicting exam score : ���� ���� ����

#### Training data set
![Alt text](C:\Users\ldy09\Documents\Deep-learning-Study\��θ����ѵ�����2/lec01����.png)
- ML�� �н������ִ� �����ͼ�.    

- ���İ��� �ٵ��� �н��� ���� ������


> ### Unsupervised learning
supervised�� �ݴ�� �̸� label�� ������ ���� ���. �����͸� ���� ������ �н���
- Google news grouping
- Word clustering

what is regression?
---
���� �� �ð��� ���� ������ ������ �����ϴ� �ý����� ���� ��.   
0~100ó�� ������ ���� �������� �����ϴ� ���� regression�̶� ��


What is classification?
---
regression�� ������ ������, �̸� �߻�ȭ(classification)�ؼ� ������.
> #### Binary classification
p/npó�� �� ���� ���� ����. �� �߿� �ϳ��� ���� ����.

> #### multi-label classification
����(A,B,C,D,F) �� �ϳ��� ���� ���� ó�� label�� ���� ���.
