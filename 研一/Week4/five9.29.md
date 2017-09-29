#上午#
-----
0.

**在 Java 集合中有两类，一类是 List，一类是 Set 他们之间的区别就在于 List 集合中的元素师有序的，且可以重复，*而 Set 集合中元素是无序不可重复的。*对于 List 好处理，但是对于 Set 而言我们要如何来保证元素不重复呢？通过迭代来 equals() 是否相等。
hashCode()作用，：**
	
	
	//Person类，
	public class Person {
        private int age;
        private int sex;    //0：男，1：女
        private String name;

        private final int PRIME = 37;

        Person(int age ,int sex ,String name){
            this.age = age;
            this.sex = sex;
            this.name = name;
        }

        /** 省略getter、setter方法 **/

        @Override
        public int hashCode() {
            System.out.println("调用hashCode方法...........");

            int hashResult = 1;
            hashResult = (hashResult + Integer.valueOf(age).hashCode() + Integer.valueOf(sex).hashCode()) * PRIME;
            hashResult = PRIME * hashResult + ((name == null) ? 0 : name.hashCode()); 
            System.out.println("name:"+name +" hashCode:" + hashResult);

            return hashResult;
        }

        /**
         * 重写hashCode()
         */
        public boolean equals(Object obj) {
            System.out.println("调用equals方法...........");

            if(obj == null){
                return false;
            }
            if(obj.getClass() != this.getClass()){
                return false;
            }
            if(this == obj){
                return true;
            }

            Person person = (Person) obj;

            if(getAge() != person.getAge() || getSex()!=   person.getSex()){
                return false;
            }

            if(getName() != null){
                if(!getName().equals(person.getName())){
                    return false;
                }
            }
            else if(person != null){
                return false;
            }
            return true;
        }
    }


     public class Main extends JPanel {

        public static void main(String[] args) {
            Set<Person> set = new HashSet<Person>();
			
			//定义四个对象p1,p2,p3,p4，实际有效的为3个，其中“张三”出现完全重复，有效对象个数为3个
            Person p1 = new Person(11, 1, "张三");
            Person p2 = new Person(12, 1, "李四");
            Person p3 = new Person(11, 1, "张三");
            Person p4 = new Person(11, 1, "李四");

            //只验证p1、p3
            System.out.println("p1 == p3? :" + (p1 == p3));
            System.out.println("p1.equals(p3)?:"+p1.equals(p3));
            System.out.println("-----------------------分割线--------------------------");
            set.add(p1);
            set.add(p2);
            set.add(p3);
            set.add(p4);
            System.out.println("set.size()="+set.size());
        }
    }


#下午#
-----

1


使用System.arraycopy()实现数组之间的复制
    System提供了一个静态方法arraycopy(),我们可以使用它来实现数组之间的复制。其函数原型是：
    
    public static void arraycopy(Object src,
     int srcPos,
     Object dest,
     int destPos,
     int length)
    
    src:源数组；	srcPos:源数组要复制的起始位置；
    
    dest:目的数组；	destPos:目的数组放置的起始位置；	length:复制的长度。
    
    注意：src and dest都必须是同类型或者可以进行转换类型的数组．
    
    有趣的是这个函数可以实现自己到自己复制，比如：
    
    int[] fun ={0,1,2,3,4,5,6}; 
    
    System.arraycopy(fun,0,fun,3,3);
    
    则结果为：{0,1,2,0,1,2,6};
    
    实现过程是这样的，先生成一个长度为length的临时数组,将fun数组中srcPos 
    
    到srcPos+length-1之间的数据拷贝到临时数组中，再执行System.arraycopy(临时数组,0,fun,3,3).
  


----
2.

    isNaN()：
    描述：返回一个 Boolean 值，指明提供的值是否是保留值 NaN （不是数字）。
    语法：isNaN(numvalue)numvalue 参数是要检查是否为 NaN 的值。
    说明：如果值是 NaN， 那么 isNaN 函数返回 true ，否则返回 false 。
**定义：**NaN（Not a Number，非数）是计算机科学中数值数据类型的一个值，表示未定义或不可表示的值。常在浮点数运算中使用。首次引入NaN的是1985年的IEEE 754浮点数标准。
链接:http://www.cnblogs.com/big-xuyue/p/4106130.html


3.

multidex

4.

Picasso是Square公司出品的一款非常优秀的开源图片加载库，是目前Android开发中超级流行的图片加载库之一



#晚上#
----
5.Rect（）

Rect位于android.graphics下，表示一个矩形，由四条边的坐标组成，

6.ScrollerCompat的简单用法。

这个是v4的组件，用法和Scroller用法差不多。第一步是调用Create方法构造对象。第二步是在computeScroll里面实现重新布局。第三步是startScroll函数。