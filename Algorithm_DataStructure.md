- ✅ Q: DFS / BFS 알고리즘에 대해서 설명해주세요. (depth 1)
    
    ### 📖 그래프 탐색이란?
    
    **루트 노드(하나의 정점) 으로부터 시작하여 차례대로 모든 노드(정점)들을 한 번씩 방문하는 것**
    
  ![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/c6ed1bb6-145a-4f5e-8d2c-1647ba52719e)
    
    ### 📖 BFS(**Breadth First Search) : 너비 우선 탐색**
    
    루트 노드에서 인접한 노드를 먼저 탐색한다.
    
    깊이가 가장 앝은 노드부터 모두 탐색하고 그 다음 깊이가 깊은 노드를 탐색한다.
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/71aa9870-0e48-4166-bbe7-ede883e83e67)
    
    ### 📖 BFS 특징
    
    두 노드 사이의 최단경로를 탐색할 때 좋다 → 멀리 떨어진 노드는 나중에 탐색하게 되기 때문이다.
    
    Queue를 이용해서 탐색 노드의 순서를 저장하고 Queue에 저장된 순서대로 탐색한다.
    
    → 왜 BFS는 Queue로 구현되는가?
    
    → 인접한 노드부터 탐색하기 때문에 FIFO 특성을 가진 Queue를 사용한다.
    
    → 하나의 레벨이 끝나면 큐에는 다음 수준의 노드들이 들어가 있음.
    
    ![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/e8cf2b00-03ae-4ea9-bf97-c38325b04246)

    ### 📖 BFS 알고리즘 구현

    ![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/71a0fd68-6cc8-4126-8fe5-d805ebc85597)

    
    1. 루트 노드 → 루트노드와 인접하고, 방문한적 없고, 큐에 없는 노드를 큐에 넣는다.
    2. 큐에서 하나의 노드를 빼서 해당 노드에 방문한다.
    
    ### 📖 BFS 실제 적용 : 인접행렬 vs 인접 리스트
    
    인접 행렬 : 그래프의 연결 관계를 이차원 배열로 나타내는 방식
    
    → 노드에서 다른 노드를 가는 간선이 있다면 1, 아니면 0으로 나타낸다.
    
    → 인접 행렬과 인접 리스트에 대한 자세한 정보는 따로 검색 추천
    
    ![인접 행렬 : 방향이 있는 그래프](https://prod-files-secure.s3.us-west-2.amazonaws.com/76f5f623-5699-487b-9e36-23d6556a29f2/956ca832-cefd-4539-8b9e-3dcde7e303a7/Untitled.png)
    
    인접 행렬 : 방향이 있는 그래프
    
    ![인접 행렬 : 방향이 없는 그래프](https://prod-files-secure.s3.us-west-2.amazonaws.com/76f5f623-5699-487b-9e36-23d6556a29f2/122b8415-73bb-4e13-bad4-f8352e0b5f76/Untitled.png)
    
    인접 행렬 : 방향이 없는 그래프
    
    인접 행렬로 구현할때 필요한 것들
    
    1. 인접행렬 배열 ( int[][] graph )
    2. 방문여부 배열 ( boolean[] visited )
    3. 큐 ( Queue queue )
    
    인접 리스트 : 그래프의 연결 관계를 리스트를 이용해서 나타내는 방식
    
    → 각 노드에 연결된 노드 번호를 리스트에 저장한다.
    
    ![인접 리스트 : 방향이 있는 그래프](https://prod-files-secure.s3.us-west-2.amazonaws.com/76f5f623-5699-487b-9e36-23d6556a29f2/008f8ee0-8aa6-48af-a68c-e373dc560e7a/Untitled.png)
    
    인접 리스트 : 방향이 있는 그래프
    
    ![인접 리스트 : 방향이 없는 그래프](https://prod-files-secure.s3.us-west-2.amazonaws.com/76f5f623-5699-487b-9e36-23d6556a29f2/496a56a9-ed19-45e3-9d4a-d4bcab35e401/Untitled.png)
    
    인접 리스트 : 방향이 없는 그래프
    
    인접 리스트로 구현할때 필요한 것들
    
    1. 인접리스트 ( ArrayList[] graph )
    2. 방문여부 배열 ( boolean[] visited )
    3. 큐 ( Queue queue )
- ✅ Q: 리스트와 같은 선형 자료구조에서 부분합을 O(n^2) 이하로 만드는 알고리즘은 무엇인가요?(depth 2)
    
    ### **1. 누적 합 (Cumulative Sum) 알고리즘**
    
    누적 합 알고리즘은 배열의 각 위치에 대해 해당 위치까지의 합을 미리 계산하여 저장하는 방법입니다. 이 방법을 사용하면, 어떤 범위의 부분합도 두 개의 인덱스를 이용해 간단히 계산할 수 있습니다.
    
    ![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/76f5f623-5699-487b-9e36-23d6556a29f2/2744c951-3891-4a6b-a7b3-eea009649ba8/Untitled.png)
    
    **구현 방법**:
    
    1. **누적 합 배열 초기화**: 주어진 배열의 크기와 동일한 누적 합 배열을 만듭니다.
    2. **누적 합 계산**: 배열의 각 요소에 대해, 이전 요소들의 합을 더하여 누적 합 배열에 저장합니다.
    3. **부분합 계산**: 특정 범위 [*i*,*j*]의 부분합을 계산할 때, 누적 합 배열에서 *j*번째 요소의 누적 합에서 *i*−1번째 요소의 누적 합을 빼면 됩니다.
    
    이 알고리즘은 누적 합 배열을 만드는 데 *O*(*n*) 시간이 걸리며, 이후 각 부분합을 *O*(1)에 계산할 수 있습니다.
    
    ### **2. 투 포인터 (Two-Pointer) 알고리즘**
    
    투 포인터 알고리즘은 특히 연속된 부분 배열에 대한 조건 (예: 합이 특정 값 이상 또는 이하)을 만족하는 부분을 찾을 때 유용합니다.
    
    **구현 방법**:
    
    1. **포인터 초기화**: 두 개의 포인터를 배열의 시작점에 위치시킵니다.
    2. **조건 검사**: 부분 배열의 합이 특정 조건을 만족할 때까지 한 포인터를 이동시킵니다.
    3. **두 번째 포인터 이동**: 조건을 만족하면 다른 포인터를 이동시켜 조건을 계속 만족하는 최소 또는 최대 길이의 부분 배열을 찾습니다.
    
    투 포인터 알고리즘은 각 요소를 한 번씩만 방문하므로 *O*(*n*) 시간 복잡도를 가집니다.
    
    https://www.lifencoding.com/algorithm/13?p=1
    
    ### **선택 기준**
    
    - **누적 합**: 여러 범위의 부분합을 반복적으로 계산해야 할 때 유리합니다.
    - **투 포인터**: 특정 조건을 만족하는 연속 부분 배열을 찾을 때 효과적입니다.
    
- ✅ Q: Heap에 대해서 설명해주세요. (depth 2)
    
    # 우선순위 큐와 힙
    
    ## 우선순위 큐
    
    일반적으로 큐(Queue)는 먼저 들어온 데이터가 먼저 나가는 선입선출(First in-First out) 구조입니다. 하지만, 우선순위 큐는 데이터가 들어온 순서가 아닌 데이터의 **우선 순위가 높은 데이터가 먼저 나가는 큐**를 말합니다. 우선순위 큐는 **주로 힙(Heap)이라는 자료구조로 구현**합니다. 또한 우선순위 큐는 **데이터의 우선 순위를 비교해야 하므로 그 데이터는 Comparable 하거나 comparator를 생성자에 넣어서 비교 연산이 가능하도록** 해야 합니다.
    
    ## 힙
    
    힙(Heap)은 완전 이진 트리에 있는 노드 중에서 키 값이 가장 큰 노드나 가장 작은 노드를 찾게 만든 자료구조입니다. 힙은 이진탐색트리와 달리 중복된 값이 허용됩니다.
    
    !https://github.com/hongcheol/CS-study/raw/main/Algorithm/img/max_heap.png
    
    - 최대 힙
        - 키 값이 가장 큰 노드를 찾기 위한 완전 이진 트리
        - 부모 노드의 키 값 >= 자식 노드의 키 값
        - 루트 노드: 키 값이 가장 큰 노드
    
    !https://github.com/hongcheol/CS-study/raw/main/Algorithm/img/min_heap.png
    
    - 최소 힙
        - 키 값이 가장 작은 노드를 찾기 위한 완전 이진 트리
        - 부모 노드의 키 값 < 자식 노드의 키 값
        - 루트 노드: 키 값이 가장 작은 노드
    - 힙에서는 루트 노드의 원소만을 삭제 할 수 있습니다.
        - 루트 노드의 원소를 삭제하여 반환한다.
        - 루트 노드를 다시 구한다.
    
    ## 힙 구현
    
    힙은 일반적으로 배열을 이용하여 구현합니다. 힙은 완전 이진 트리이므로 중간에 비어있는 요소가 없기 때문에 배열의 공간을 모두 사용하기 때문입니다.
    
    !https://github.com/hongcheol/CS-study/raw/main/Algorithm/img/heap.png
    
    **자식노드를 구하고 싶을 때**
    
    - 왼쪽 자식노드 index = (부모 노드 index) * 2
    - 오른쪽 자식노드 index = (부모 노드 index) * 2 + 1
    
    **부모노드를 구하고 싶을 때**
    
    - 부모 노드 index = (자식노드 index) / 2
    
    ### 삽입
    
    힙에 데이터를 삽입하는 방법은 다음과 같습니다.
    
    1. 완전 이진트리의 마지막 노드에 이어서 새로운 노드를 추가한다.
    2. 추가된 새로운 노드를 부모의 노드와 비교하여 교환한다.
    3. 힙 구조를 만족할 때 까지 2를 반복한다.
    
    힙에 3을 삽입하는 과정은 다음과 같습니다.
    
    !https://github.com/hongcheol/CS-study/raw/main/Algorithm/img/heap_insert.png
    
    ### 삭제
    
    힙에서 데이터를 삭제하는 방법은 다음과 같습니다.
    
    1. 루트 노드가 가장 우선 순위가 높으므로 루트 노드를 삭제한다.
    2. 루트 노드가 삭제된 빈자리에 완전 이진트리의 마지막 노드를 가져온다.
    3. 루트 자리에 위치한 새로운 노드를 자식 노드와 비교하여 교환한다.
    4. 힙 구조를 만족할 때 까지 3을 반복한다.
    
    !https://github.com/hongcheol/CS-study/raw/main/Algorithm/img/heap_delete.png
    
    ## 힙의 시간 복잡도와 우선순위 큐를 힙으로 구현하는 이유
    
    우선순위 큐 == 힙이 아닙니다. 힙은 우선순위 큐를 구현할 수 있는 여러 자료구조 중 하나입니다. 하지만 우선순위 큐는 보통 힙으로 구현합니다. 그 이유는 시간 복잡도에서 가장 유리하기 때문입니다.
    
    만약 배열로 구현한다면 우선 순위가 높은 순서대로 배열의 가장 앞부분부터 넣을 때 우선 순위가 높은 데이터는 맨 앞의 index를 이용하는 것으로 쉽게 찾을 수 있습니다. 하지만 우선 순위가 중간인 데이터를 삽입한다면 삽입하는 위치를 찾고, 뒤의 데이터를 모두 한 칸 씩 밀어야 합니다. 그러므로 정렬된 배열에서는 삽입은 O(n), 삭제는 O(1)의 시간 복잡도를 가집니다. 정렬되지 않은 배열이라면 삽입은 O(1)이고, 삭제할 때 삭제할 값을 찾아야 하므로 O(n)의 시간 복잡도를 가집니다.
    
    연결리스트로 구현할 때도 배열과 크게 다르지 않습니다. 정렬 유무에 따라 배열과 같은 시간 복잡도를 가집니다.
    
    하지만 힙으로 구현한다면 삽입과 삭제과정에서 모두 부모 노드와 자식 노드 간의 비교만 이뤄지므로 O(log2n)의 시간 복잡도를 가집니다.
    
    정리하면 배열과 연결리스트는 정렬 여부에 따라 삽입과 삭제에서 O(n)과 O(1)의 시간 복잡도를 가지게 되고, 힙은 일관적으로 O(log2n)의 시간복잡도를 가집니다. 그래서 편차가 심한 배열과 연결리스트 보다는 힙으로 구현을 합니다.
    

- ✅ **다음 코드의 시간복잡도를 계산해주세요.**
    
    ```java
    int fobonacchi(int k) {
    	if (k <= 1) {
    		return k;
    	}
    
    	return fibonacchi(k - 2) + fibonacchi(k - 1);
    }
    ```
    
    - **답변**
        - 예제 코드의 시간복잡도는 `**O(2^n)**`입니다.
            - 트리 깊이 k = 7 (n)
            - 재귀 함수를 2번 호출 (차수를 가짐)
            - 따라서 빅 오는 `O(차수^깊이)`로 표현 가능
        - 더 정확한 답변으로는 실제값이 2보다 작다는 것을 언급하면 좋습니다.
            - 단일 호출만 갖기도 하는 트리 맨 아래의 마지막 수준을 고려해야 합니다.
        
        - 공간복잡도 측면에서 빅 오는 `O(n)` 입니다.
        - 동적 프로그래밍, 메모이제이션을 이용하면 시간복잡도를 O(n)으로 줄일 수 있습니다.
        
        출처: 자바 코딩 인터뷰 완벽 가이드(https://www.yes24.com/Product/Goods/111393077)
        
- ✅ **Stack을 코드로 구현해주세요.**
    
    
    - 스택은 `후입선출(LIFO)` 원칙을 따르는 선형 자료구조 입니다.
    - 스택에서 요소는 한 쪽 끝(top)에서만 추가 및 제거할 수 있습니다.
    
    Stack은 LinkedList 또는 배열을 기반으로 구현할 수 있습니다.
    
    - 코드
        
        ```java
        import java.util.EmptyStackException;
        
        public class Stack<T> {
        	public class Node<T> {
        		private final T data;
        		private Node<T> next;
        
        		public Node(T data) {
        			this.data = data;
        		}
        	}
        
        	private Node<T> top;
        
        	public T pop() {
        		if (top == null) {
        			throw new EmptyStackException();
        		}
        
        		T item = top.data;
        		top = top.next;
        
        		return item;
        	}
        
        	public void push(T item) {
        		Node<T> t = new Node<>(item);
        		t.next = top;
        		top = t;
        	}
        
        	public T peek() {
        		if (top == null) {
        			throw new EmptyStackException();
        		}
        
        		return top.data;
        	}
        
        	public boolean isEmpty() {
        		return top == null;
        	}
        }
        ```
        
        ```java
        import java.lang.reflect.Array;
        import java.util.Arrays;
        import java.util.EmptyStackException;
        import java.util.Stack;
        
        public final class Stack1<E> {
        	private static final int DEFAULT_CAPACITY = 10;
        
        	private int top;
        	private E[] stack;
        
        	// 리플렉션
        	Stack1() {
        		stack = (E[])Array.newInstance(
        			Object[].class.getComponentType(), DEFAULT_CAPACITY
        		);
        
        		top = 0;
        	}
        
        	public void push(E e) {
        		if (isFull()) {
        			ensureCapacity();
        		}
        
        		stack[top++] = e;
        	}
        
        	public E pop() {
        		if (isEmpty()) {
        			throw new EmptyStackException();
        		}
        
        		E e = stack[--top];
        		stack[top] = null;
        
        		return e;
        	}
        
        	public E peek() {
        		if (isEmpty()) {
        			throw new EmptyStackException();
        		}
        
        		return stack[top - 1];
        	}
        
        	public int size() {
        		return stack.length;
        	}
        
        	public boolean isEmpty() {
        		return top == 0;
        	}
        
        	public boolean isFull() {
        		return top == stack.length;
        	}
        
        	public void ensureCapacity() {
        		int newSize = stack.length * 2;
        		stack = Arrays.copyOf(stack, newSize);
        	}
        }
        ```
        
    
    출처:
    
    자바 코딩 인터뷰 완벽 가이드(https://www.yes24.com/Product/Goods/111393077)
    
    엔지니어 대한민국(https://youtu.be/whVUYv0Leg0?si=-WXThQ1QRUHsbDEW)
    
- ✅ **버블 정렬에 대해 설명해주세요.**
    - 버블 정렬은 배열의 원소가 완전히 정렬될 때까지 서로 인접한 두 원소를 비교해 정렬하는 알고리즘입니다.
    - 배열의 전체 길이(n)의 0번 인덱스부터 n-1번 인덱스까지 모든 인덱스를 비교하며 정렬합니다.
    - 시간복잡도는 `**O(n^2)**` 입니다.
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/23e0d6c4-99d4-4302-a7f9-6e5186ec1969)
    
    ```python
    def bubble_sort(list)：
    	unsorted_until_index = len(list) - 1
    	sorted = False
    
    	while not sorted：
    		sorted = True
    		for i in range(unsorted_until_index)：
    			if list[i] 〉 list[i+1]:
    				list[i], list[i+1] = list[i+1], list[i]
    				sorted = False
    		unsorted_until_index -= 1
    
    return list
    ```
    
    출처: 
    
    누구나 자료 구조와 알고리즘(https://www.yes24.com/Product/Goods/105122143)
    
    망나니 개발자(https://dev-coco.tistory.com/160)
    
- ✅ **삽입 정렬에 대해 설명해주세요.**
    - 삽입 정렬은 두 번째 값부터 시작해 그 앞에 존재하는 원소들과 비교하여 삽입할 위치를 찾아 삽입하는 정렬 알고리즘입니다.
    - 평균 시간복잡도는 `**O(n^2)**`이며, Best Case의 경우 `O(n)`까지 낮아질 수 있습니다
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/21dd6224-7bc6-4704-8e4b-13ac104794f4)
    
    출처: 망나니 개발자(https://dev-coco.tistory.com/160)
    
- ✅ **DFS와 BFS의 차이점에 대해 말씀해주세요.**
    
    **DFS(Depth-First Search, 깊이 우선 탐색)**
    
    - 그래프에서 깊은 부분을 우선으로 탐색하는 알고리즘입니다.
    - DFS 구현은 `후입선출(LIFO)` 방식인 **스택**을 이용할 수 있습니다.
        - (재귀를 사용하면 간결하게 구현할 수 있습니다.)
    
    **BFS(Breadth-First Search, 너비 우선 탐색)**
    
    - 그래프에서 가까운 노드부터 탐색하는 알고리즘입니다.
    - BFS 구현은 `선입선출(FIFO)` 방식인 **큐**를 이용할 수 있습니다.
        - 해당 노드의 인접 노드 중 방문하지 않은 노드를 모두 큐에 넣는 방식으로, 가까운 노드부터 탐색할 수 있습니다.
    
    |  | DFS | BFS |
    | --- | --- | --- |
    | 동작 원리 | LIFO(스택) | FIFO(큐) |
    | 구현 방법 | 재귀 함수 이용 | 큐 자료구조 이용 |
    | 시간 복잡도 | O(V+E)
    V: 노드 개수
    E: 간선 개수 | O(N) |
    
    출처: 이것이 취업을 위한 코딩테스트다(https://www.yes24.com/Product/Goods/91433923)
    

- ✅ Hash Table에 대해서 설명해주세요.
    
    Array 자료구조에 저장된 n개의 색상 정보 중에, 특정 색상의 값을 검색하는 경우에, 검색 / 삽입 / 삭제 연산에 평균 $O(n)$의 시간복잡도를 갖게 됩니다. 
    
    이 때, Hash Table은 $O(1)$의 시간복잡도로 key 값과 value 값을 직접 조회할 수 있습니다.
    
    즉 검**색 / 삽입 / 삭제 작업에 효율적인 자료구조** 중 하나로, 평균 $O(1)$의 시간복잡도로 **Key-value 형태의 값을 저장하고 검색**할 수 있습니다.
    
    ### 동작원리는요?
    
    Hash Table에 데이터를 추가하거나 조회할 때, Hash Function을 사용합니다. Hash Table에서 해시 함수는 입력된 Key를 table의 크기에 적합한 인덱스 값으로 변환하는 것이 목적입니다. 따라서 출력의 길이(인덱스 범위)는 해시 테이블의 크기에 의존적입니다. 예를 들어, 크기가 10인 해시 테이블에서 사용하는 해시 함수의 출력 범위는 0부터 9까지입니다.
    
    - Hash Fuction
        
        hash 테이블에서 해시함수는 key 값을 입력 받아 Hash table 사의 주소 값을 반환한다. 즉 입력 키를 해시 테이블 전체에 고루 분산시켜 주는 함수가 좋은 해시 함수이다. 
        
        해시 테이블에서 사용하는 해시 함수가 해시 코드를 계산하는 방법은 간단한 방식부터 복잡하고 최적화된 방식까지 다양합니다. 여기서는 각 문자열의 문자들의 ASCII 값을 합하여 해시 코드 만드는 Hash 함수를 설명하겠습니다. (가장 간단)
        
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/7e57297d-c02f-4a0c-9b0f-3739ab9deb4c)
        
    
    ex) 강(44053) + 호(54812) + 동(46020) = 144885
    강호동 : 144885 (해시 코드) % 7 = 4 (해시 테이블의 인덱스)
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/7c434a27-33f9-492d-bc9d-6953bc03a212)
    
    ### **Hash Table의 장점과 단점 말해주세요**
    
    - 장점
        - 빠른 데이터 접근 속도 : 평균적으로 O(1)의 시간 복잡도로 조회 / 삽입 / 삭제를 수행
        - 키-값 쌍 저장 : 키를 기반으로 데이터를 저장하고 검색하는 구조로, 데이터의 연관 관계를 보다 명확하고 쉽게 관리할 수 있음
        - 중복 방지 : 키의 유일성을 통해 데이터의 중복을 자연스럽게 방지
    - 단점
        - `두 개 이상의 키가 동일한 해시 값을 가질 경우 충돌이 발생합니다.` 충돌을 관리하는 많은 방법들이 있지만, 충돌이 빈번하게 발생할 경우 성능 저하를 가져올 수 있습니다.
- ✅ **해시 테이블에서 충돌이 발생할 경우 어떻게 처리하나요?**
    
    ### **`Hash Collision이란?`**
    
    해시 테이블 내에 어떤 키가 이미 자리 잡고 있는 상태에서 다른 키가 삽입을 시도하는 경우에, 해시 함수가 서로 다른 입력에 대해 동일한 값을 반환하는 경우 Hash Collision 발생합니다.
    
    ### **Hash Collision이 발생하는 이유**
    
    - 해시 함수는 임의의 크기의 입력을 고정 크기의 해시 값으로 변환합니다.
    - 이때, 해시 함수의 출력 공간이 입력 공간보다 작을 수 있기 때문에 해시 충돌이 발생할 수 있습니다.
    - 예를 들어서, 입력값이 문자열이고 값이 저장되는 배열의 index 값은 정수일 때, 문자열의 값은 무한히 큰데 반해 정수값의 범위는 table의 크기로 상대적으로 작게 고정되어 있기 때문입니다.
    
    ### 해결법 1 **`Separate Chaning`**
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/9d1376ac-8352-4f09-8141-677f20baa4de)
    
    - 같은 주소로 해싱되어 **충돌이 일어나는 Entry를 연결 리스트(Linked List)로 연결**해서 저장하는 방식으로 해시 충돌을 피할 수 있습니다.
    - Chaning 방법에서 임의의 키에 해당하는 엔트리를 저장할 때는 해시값이 가리키는 bucket의 연결 리스트에 삽입 합니다.
    - 이때 내가 사용하고 있는 연결 리스트의 구현체에 따라서 맨 앞 혹은 끝에 삽입하는 것이 좋습니다.
    
    > 그림을 설명하자면, 해시 테이블 구조를 보여주고 있습니다. 여기서 'keys'는 데이터를 식별하는데 사용되는 고유한 값들을 나타내며, 'buckets'는 해시 함수에 의해 계산된 해시 값에 따라 데이터를 저장하는 위치를 나타냅니다. 'overflow entries'는 충돌이 발생했을 때 추가 데이터를 저장하는 영역을 나타냅니다.
    > 
    
    > 이 경우, John Smith와 Sandra Dee의 이름이 해시 함수에 의해 동일한 버킷 번호인 152로 해시되었습니다. 이것은 '해시 충돌'이라고 부릅니다. 해시 테이블은 충돌을 처리하기 위해 여러 방법을 사용할 수 있는데, 그 중 하나가 '체이닝(chaining)'입니다. 체이닝은 같은 버킷에 속하는 항목들을 연결 리스트로 만드는 것입니다.
    > 
    
    > 그림에 나타난 것처럼, John Smith와 Sandra Dee는 같은 버킷 152에 링크드 리스트로 연결되어 있습니다. 이 경우, 버킷 152에서 John Smith의 데이터를 찾은 다음, 연결 리스트를 따라가 Sandra Dee의 데이터를 찾아야 합니다. 각 항목을 찾을 때는 해시 테이블에 저장된 키 값과 실제 찾고자 하는 키 값을 비교하여 정확한 데이터를 찾습니다.
    > 
    
    > 따라서, Sandra Dee의 전화번호를 찾기 위해서는 먼저 버킷 번호 152로 이동한 다음, 연결 리스트를 따라가면서 'Sandra Dee'라는 키 값을 가진 항목을 찾아야 합니다. 이 과정에서 John Smith의 키 값과는 다르므로 이를 건너뛰고 Sandra Dee에 해당하는 항목을 찾아 데이터에 접근하게 됩니다.
    > 
    
    ### 해결법 2 **`Open Addressing`**
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/e969c598-2f31-4aa3-96ef-0311d16d0148)
    
    - Separate Chaning 방식과 달리 추가 공간을 사용하지 않고 충돌을 해결하는 방법입니다.
    - 해시 출돌이 일어나도 정해진 hash table 공간에 다른 위치에 저장합니다. 이러한 특징 때문에 데이터가 key의 해시 결과 반환되는 bucket의 인덱스와 일치하는 주소에 저장된다는 보장은 없습니다.
    - 개방 주소법(Open Addressing)에서 엔트리(Key-value pair)를 해시 테이블에 삽입하는 과정
        - 해시(key) → 해시 충돌 발생 X → 해시 결과 반환된 bucket 위치에 저장
        - 해시(key) → 해시 충돌 발생 O → **정해진 규칙에 의해 다음 자리를 찾아** 저장
    
    1. **선형 탐색 (Linear Probing) <이정도만 해도 괜찮을 듯합니다>**
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/5ad66539-dd77-4aca-8d4f-a77768140ef1)
    
![image](https://github.com/CodeSquad-2023-BE-Study/InterviewStudy/assets/53938366/5edf2cab-e0bc-4c2c-be4f-06227a004d97)
    
    - 이차원 탐색 (Quadratic Probing)
    - 더블 해싱 (Double Hashing)
- ✅ Load Factor**가 무엇을 의미하나요? 그리고 Load Factor가 성능에 어떤 영향을 미치나요?**
    
    **Load Factor**는 해시 테이블에 저장된 항목의 수를 해시 테이블의 전체 크기로 나눈 값으로, **해시 테이블의 "가득 찬 정도"를 나타냅**니다. 예를 들어, 로드 팩터가 0.5라면 해시 테이블의 절반만 항목으로 채워져 있다는 것을 의미합니다.
    
    Separate Chaining과 Open Addressing 모두에서 Load Factor는 중요한 역할을 합니다. 그러나 각 방식에서 Load Factor의 의미와 그에 따른 영향이 약간 다릅니다.
    
    1. **Separate Chaining**:
        - **Load Factor가 증가하면 각 버킷에 저장된 연결 리스트의 평균 길이가 길어집니다.**
        - **검색 성능은 load factor에 비례해서 저하될 수 있습니다.**
        - 이로 인해 충돌 시 처리하는 데 필요한 시간이 증가할 수 있습니다.
        - 따라서, Load Factor가 특정 임계값 (예: 0.75)을 초과하면 해시 테이블의 크기를 늘려서 리사이징하는 것이 일반적입니다.
    2. **Open Addressing**:
        - Load Factor가 증가하면 해시 **테이블 내의 사용 가능한 빈 슬롯이 줄어들게 됩니다. 이로 인해 새로운 항목을 삽입하거나 기존 항목을 찾을 때 발생하는 충돌의 수가 증가**하게 되며, 이는 성능 저하로 이어질 수 있습니다.
        - 검색 성능은 load factor가 1에 가까워 질 수록 급속하게 커진다.
    - Open Addressing에서는 Load Factor가 너무 높아지면 성능이 크게 저하될 수 있으므로, 일반적으로 Load Factor의 임계값을 Separate Chaining보다 낮게 설정합니다 (예: 0.5 또는 0.6).
    
    결론적으로, 두 해시 테이블 구현 방식 모두에서 Load Factor는 중요한 역할을 합니다. 
    
- ✅ **해시 테이블에서 "동적 리사이징"이 무엇이며, 언제 필요한가요?**
    
    동적 리사이징은 해시 테이블의 크기를 동적으로 조정하는 과정입니다. 초기에 할당된 배열의 크기가 고정되어 있기 때문에, 데이터의 양이 증가하면서 배열의 크기를 초과할 가능성이 있습니다. 이럴 때, 해시 테이블의 크기를 증가시켜 (보통 두 배로) 새로운, 더 큰 배열에 기존의 데이터를 재해시하여 저장하는 과정을 동적 리사이징이라고 합니다.
    
    동적 리사이징은 주로 해시 테이블의 로드 팩터가 특정 임계값 (예: 0.75)을 초과할 때 발생합니다. 로드 팩터는 해시 테이블에 저장된 항목의 수를 해시 테이블의 전체 크기로 나눈 값입니다. 로드 팩터가 높아지면 충돌의 확률이 증가하므로, 동적 리사이징을 통해 이를 해결하려고 합니다.
