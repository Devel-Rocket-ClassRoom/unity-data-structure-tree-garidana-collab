### 핵심 포인트

- **두 제네릭 타입**: 저장할 원소 타입 `TElement`와 우선순위 비교용 `TPriority`. 분리해 두면 원소 자체가 비교 가능할 필요가 없다 (예: `GraphNode`를 우선순위 `int`로 정렬).
- 비교는 `Comparer<TPriority>.Default`로 수행. `int`, `string`, `float` 등 표준 타입은 자동으로 오름차순 비교자가 적용돼 **Min-Heap**이 된다.
- 내부 저장소는 `List<(TElement Element, TPriority Priority)>` — **튜플**로 두 값을 엮어 저장.
- `Dequeue`는 원소만 반환 — 우선순위는 내부 동작에 쓸 뿐 외부 반환값 아님.


public class PriorityQueue<TElement, TPriority>
{
    public int Count { get; }

    public void Enqueue(TElement element, TPriority priority);
    public TElement Dequeue();
    public TElement Peek();
    public void Clear();
}