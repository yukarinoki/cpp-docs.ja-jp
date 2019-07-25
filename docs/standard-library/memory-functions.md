---
title: '&lt;memory&gt; 関数'
ms.date: 02/06/2019
f1_keywords:
- memory/std::addressof
- memory/std::align
- memory/std::allocate_shared
- memory/std::const_pointer_cast
- memory/std::declare_no_pointers
- memory/std::declare_reachable
- memory/std::default_delete
- memory/std::dynamic_pointer_cast
- memory/std::get_deleter
- memory/std::get_pointer_safety
- xmemory/std::get_temporary_buffer
- memory/std::make_shared
- memory/std::make_unique
- memory/std::owner_less
- xmemory/std::return_temporary_buffer
- memory/std::static_pointer_cast
- memory/std::swap
- memory/std::undeclare_no_pointers
- memory/std::undeclare_reachable
- memory/std::uninitialized_copy
- memory/std::uninitialized_copy_n
- memory/std::uninitialized_fill
- memory/std::uninitialized_fill_n
- memory/std::get_temporary_buffer
- memory/std::return_temporary_buffer
ms.assetid: 3e1898c2-44b7-4626-87ce-84962e4c6f1a
helpviewer_keywords:
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::swap [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
- std::addressof [C++]
- std::align [C++]
- std::allocate_shared [C++]
- std::const_pointer_cast [C++]
- std::declare_no_pointers [C++]
- std::declare_reachable [C++]
- std::default_delete [C++]
- std::dynamic_pointer_cast [C++]
- std::get_deleter [C++]
- std::get_pointer_safety [C++]
- std::get_temporary_buffer [C++]
- std::make_shared [C++]
- std::make_unique [C++]
- std::owner_less [C++]
- std::return_temporary_buffer [C++]
- std::static_pointer_cast [C++]
- std::undeclare_no_pointers [C++]
- std::undeclare_reachable [C++]
- std::uninitialized_copy [C++]
- std::uninitialized_copy_n [C++]
- std::uninitialized_fill [C++]
- std::uninitialized_fill_n [C++]
ms.openlocfilehash: 14818e93e79a0be9960ba67088f81d51d402b717
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448488"
---
# <a name="ltmemorygt-functions"></a>&lt;memory&gt; 関数

## <a name="addressof"></a>addressof

オブジェクトの実際のアドレスを取得します。

```cpp
template <class T>
    T* addressof(T& Val);
```

### <a name="parameters"></a>パラメーター

*Val*\
実際のアドレスを取得する対象のオブジェクトまたは関数。

### <a name="return-value"></a>戻り値

オーバーロード`operator&()`されたが存在する場合でも、 *Val*によって参照されるオブジェクトまたは関数の実際のアドレス。

### <a name="remarks"></a>Remarks

## <a name="align"></a>位置

特定のサイズの記憶域 (特定のアラインメント指定でアラインされた) を、特定の記憶域の最初に使用可能なアドレスに合わせてアラインします。

```cpp
void* align(
    size_t Alignment, // input
    size_t Size,      // input
    void*& Ptr,        // input/output
    size_t& Space     // input/output
);
```

### <a name="parameters"></a>パラメーター

*配置*\
試行するアラインメントの境界。

*幅*\
アラインされたストレージのサイズ (バイト単位)。

*ポインター*\
使用する利用可能な一連の記憶域プールの開始アドレス。 このパラメーターは出力パラメーターでもあり、アラインメントが成功した場合は新しい開始アドレスを格納するように設定されます。 `align()` が失敗した場合、このパラメーターは変更されません。

*行間*\
アラインされた記憶域の作成に使用する `align()` で利用可能な合計領域。 このパラメーターは出力パラメーターでもあり、アラインされたストレージと関連するオーバーヘッドが差し引かれた後の記憶域バッファーに残されている調整された領域を格納します。

`align()` が失敗した場合、このパラメーターは変更されません。

### <a name="return-value"></a>戻り値

要求されたアラインバッファーが使用可能な領域に収まりきらない場合は null ポインター。それ以外の場合は、 *Ptr*の新しい値。

### <a name="remarks"></a>Remarks

変更された*Ptr*および*空間*パラメーターを使用`align()`すると、同じバッファーでを繰り返し呼び出すことができます。これは、*アラインメント*と*サイズ*の値が異なる場合があります。 `align()` の使用方法の 1 つを次のコード スニペットに示します。

```cpp
#include <type_traits> // std::alignment_of()
#include <memory>
//...
char buffer[256]; // for simplicity
size_t alignment = std::alignment_of<int>::value;
void * ptr = buffer;
std::size_t space = sizeof(buffer); // Be sure this results in the true size of your buffer

while (std::align(alignment, sizeof(MyObj), ptr, space)) {
    // You now have storage the size of MyObj, starting at ptr, aligned on
    // int boundary. Use it here if you like, or save off the starting address
    // contained in ptr for later use.
    // ...
    // Last, move starting pointer and decrease available space before
    // the while loop restarts.
    ptr = reinterpret_cast<char*>(ptr) + sizeof(MyObj);
    space -= sizeof(MyObj);
}
// At this point, align() has returned a null pointer, signaling it is not
// possible to allow more aligned storage in this buffer.
```

## <a name="allocate_shared"></a>allocate_shared

指定されたアロケーターを使用することによって、特定の型に割り当てられ構築されたオブジェクトに対して `shared_ptr` を作成します。 `shared_ptr` を返します。

```cpp
template <class Type, class Allocator, class... Types>
    shared_ptr<Type> allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>パラメーター

*割り当て*\
オブジェクトを作成するために使用されるアロケーター。

*Value*\
オブジェクトになるゼロ個以上の引数。

### <a name="remarks"></a>Remarks

関数は、 *Alloc*に`shared_ptr<Type>`よって割り当てら`Type(Args...)`れて構築されたオブジェクト、へのポインターを作成します。

## <a name="atomic_compare_exchange_strong"></a>atomic_compare_exchange_strong

```cpp
template<class T>
    bool atomic_compare_exchange_strong(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_weak"></a>atomic_compare_exchange_weak

```cpp
template<class T>
    bool atomic_compare_exchange_weak(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w);
```

## <a name="atomic_compare_exchange_strong_explicit"></a>atomic_compare_exchange_strong_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_strong_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_compare_exchange_weak_explicit"></a>atomic_compare_exchange_weak_explicit

```cpp
template<class T>
    bool atomic_compare_exchange_weak_explicit(shared_ptr<T>* p, shared_ptr<T>* v, shared_ptr<T> w, memory_order success, memory_order failure);
```

## <a name="atomic_exchange"></a>atomic_exchange

```cpp
template<class T>
    shared_ptr<T> atomic_exchange(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_exchange_explicit"></a>atomic_exchange_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_exchange_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="atomic_is_lock_free"></a>atomic_is_lock_free

```cpp
template<class T>
    bool atomic_is_lock_free(const shared_ptr<T>* p);
```

## <a name="atomic_load"></a>atomic_load

```cpp
template<class T>
    shared_ptr<T> atomic_load(const shared_ptr<T>* p);
```

## <a name="atomic_load_explicit"></a>atomic_load_explicit

```cpp
template<class T>
    shared_ptr<T> atomic_load_explicit(const shared_ptr<T>* p, memory_order mo);
```

## <a name="atomic_store"></a>atomic_store

```cpp
template<class T>
    void atomic_store(shared_ptr<T>* p, shared_ptr<T> r);
```

## <a name="atomic_store_explicit"></a>atomic_store_explicit

```cpp
template<class T>
    void atomic_store_explicit(shared_ptr<T>* p, shared_ptr<T> r, memory_order mo);
```

## <a name="const_pointer_cast"></a>const_pointer_cast

shared_ptr への const キャスト。

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

*~* \
返される共有ポインターによって制御される型。

*他の*\
引数の共有ポインターによって制御される型。

*他の*\
引数の共有ポインター。

### <a name="remarks"></a>Remarks

このテンプレート関数は、が null ポインターを`const_cast<Ty*>(sp.get())`返す場合は空の shared_ptr オブジェクトを返します。それ以外の場合は、によって所有さ`sp`れているリソースを所有する[shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty > オブジェクトを返します。 式 `const_cast<Ty*>(sp.get())` は有効な式である必要があります。

### <a name="example"></a>例

```cpp
// std__memory__const_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int);
    std::shared_ptr<const int> sp1 =
        std::const_pointer_cast<const int>(sp0);

*sp0 = 3;
    std::cout << "sp1 == " << *sp1 << std::endl;

    return (0);
}
```

```Output
sp1 == 3
```

## <a name="declare_no_pointers"></a>declare_no_pointers

ベース アドレス ポインターとブロック サイズで定義されたメモリ ブロック内の文字に追跡可能なポインターが含まれていないことを、ガベージ コレクターに通知します。

```cpp
void declare_no_pointers(char* ptr, size_t _Size);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
追跡可能なポインターがもう含まれない最初の文字のアドレス。

*サイズ (_s)* \
トレース可能なポインターを含まない、 *ptr*で開始されるブロックのサイズ。

### <a name="remarks"></a>Remarks

関数は、アドレス`[ ptr, ptr + _Size)`の範囲に追跡可能なポインターが含まれないことをガベージコレクターに通知します。 (割り当てられたストレージへのポインターは、到達可能な場合を除き、逆参照しないでください)。

## <a name="declare_reachable"></a>declare_reachable

指定されたアドレスが、割り当てられたストレージのアドレスであり、そのストレージに到達可能であることをガベージ コレクションに通知します。

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
到達可能な割り当て済みの有効なストレージ領域へのポインター。

### <a name="remarks"></a>Remarks

*Ptr*が null でない場合、関数は、 *ptr*が到達可能である (有効な割り当て済みストレージを指す) ことをガベージコレクターに通知します。

## <a name="default_delete"></a>default_delete

**Operator new**で割り当てられたオブジェクトを削除します。 `unique_ptr` での使用に適しています。

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
        default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>パラメーター

*ポインター*\
削除するオブジェクトへのポインター。

*他の*\
削除対象の配列内の要素の型。

### <a name="remarks"></a>Remarks

このテンプレートクラスは、 `deleter` **new 演算子**で割り当てられたスカラーオブジェクトを削除するを記述し`unique_ptr`ます。これは、テンプレートクラスでの使用に適しています。 明示的な特殊化 `default_delete<Type[]>` もあります。

## <a name="destroy_at"></a>destroy_at

```cpp
template <class T>
    void destroy_at(T* location);
```

`location->~T()` と同じ。

## <a name="destroy"></a>倒す

```cpp
template <class ForwardIterator>
    void destroy(ForwardIterator first, ForwardIterator last);
```

`for (; first!=last; ++first) destroy_at(addressof(*first)); ` と同じ。

## <a name="destroy_n"></a>destroy_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator destroy_n(ForwardIterator first, Size n);
```

`for (; n > 0; (void)++first, --n) destroy_at(addressof(*first)); return first;` と同じ。

## <a name="dynamic_pointer_cast"></a>dynamic_pointer_cast

shared_ptr への動的なキャストを実行します。

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

*~* \
返される共有ポインターによって制御される型。

*他の*\
引数の共有ポインターによって制御される型。

*プロセッサー*\
引数の共有ポインター。

### <a name="remarks"></a>Remarks

このテンプレート関数は、が null ポインターを`dynamic_cast<Ty*>(sp.get())`返す場合は空の shared_ptr オブジェクトを返し、それ以外の場合は、 *sp*によって所有されているリソースを所有する[shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty > オブジェクトを返します。 式 `dynamic_cast<Ty*>(sp.get())` は有効な式である必要があります。

### <a name="example"></a>例

```cpp
// std__memory__dynamic_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    virtual ~base() {}
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::dynamic_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="get_deleter"></a>get_deleter

shared_ptr から削除子を取得します。

```cpp
template <class D, class Ty>
    D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>パラメーター

*A*\
削除子の型。

*~* \
共有ポインターによって制御される型。

*プロセッサー*\
共有ポインター。

### <a name="remarks"></a>Remarks

このテンプレート関数は、 [Shared_ptr クラス](../standard-library/shared-ptr-class.md)オブジェクト*sp*に属する型*D*の削除子へのポインターを返します。 *Sp*に削除子がない場合、またはその削除子が*D*型でない場合、関数は0を返します。

### <a name="example"></a>例

```cpp
// std__memory__get_deleter.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct deleter
{
    void operator()(base *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<base> sp0(new base);

    sp0->val = 3;
    std::cout << "get_deleter(sp0) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp0) != 0) << std::endl;

    std::shared_ptr<base> sp1(new base, deleter());

    sp0->val = 3;
    std::cout << "get_deleter(sp1) != 0 == " << std::boolalpha
        << (std::get_deleter<deleter>(sp1) != 0) << std::endl;

    return (0);
}
```

```Output
get_deleter(sp0) != 0 == false
get_deleter(sp1) != 0 == true
```

## <a name="get_pointer_safety"></a>get_pointer_safety

ガベージ コレクターが想定するポインターの安全性の種類を返します。

```cpp
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Remarks

関数は、自動ガベージコレクターが想定するポインターの安全性の種類を返します。

## <a name="get_temporary_buffer"></a>get_temporary_buffer

指定した要素数を上限とする要素シーケンスに対し、一時的なストレージを割り当てます。

```cpp
template <class Type>
    pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>パラメーター

*数*\
メモリの割り当て対象となる、必要な要素の最大数。

### <a name="return-value"></a>戻り値

最初のコンポーネントが割り当て済みのメモリへのポインターで、2 番目のコンポーネントがバッファーのサイズ指定である `pair`。これで、格納可能な要素の最大数が示されます。

### <a name="remarks"></a>Remarks

この関数はメモリを要求しますが、成功しない場合もあります。 バッファーが割り当てられなかった場合、関数は、2 番目のコンポーネントが 0 で、最初のコンポーネントが Null ポインターである pair を返します。

この関数は、一時的なメモリにのみ使用する必要があります。

### <a name="example"></a>例

```cpp
// memory_get_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300, 1000, 2000 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
      << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
        << "could store is given by: resultPair.second = "
        << resultPair.second << "." << endl;
}
```

```Output
The number of integers in the array is: 9.
The number of elements that the allocated memory
could store is given by: resultPair.second = 9.
```

## <a name="make_shared"></a>make_shared

既定のアロケーターを使用してゼロ以上の引数から構築された割り当て済みオブジェクトを指し示す `shared_ptr` を作成し、返します。 指定された型のオブジェクトおよび `shared_ptr` の両方を割り当て構築することでオブジェクトの共有所有権を管理し、`shared_ptr` を返します.

```cpp
template <class Type, class... Types>
    shared_ptr<Type> make_shared(Types&&... _Args);
```

### <a name="parameters"></a>パラメーター

*引数 (_s)* \
0 個以上のコンストラクター引数。 関数は、提供された引数に基づいてどのコンストラクターのオーバーロードを呼び出すかを推測します。

### <a name="remarks"></a>Remarks

オブジェクトを作成するための簡単で効率的な方法として `make_shared` を使用し、同時にオブジェクトへの共有アクセスを管理するために `shared_ptr` を使用します。 意味的には、これら 2 つのステートメントは同等です。

```cpp
auto sp = std::shared_ptr<Example>(new Example(argument));
auto msp = std::make_shared<Example>(argument);
```

しかし、最初のステートメントで 2 つの割り当てが実行され、`shared_ptr` オブジェクトが正常に完了した後、`Example` の割り当てが失敗すると、名前のない `Example` オブジェクトがリークされます。 `make_shared` を使用するステートメントの方が、関数呼び出しが 1 つしか関係しないので簡単です。 ライブラリがオブジェクトとスマート ポインターの両方に対して単一の割り当てを行うことができるため効率的です。 こちらの方が高速でメモリの断片化が少なくなります、1 つは割り当てられてもう 1 つは割り当てられないという例外が発生する可能性はありません。 スマート ポインターでオブジェクトを参照したり参照カウントを更新したりするコードでは、局所性の改善によってパフォーマンスが向上します。

オブジェクトへの共有アクセスを必要としない場合、[make_unique](../standard-library/memory-functions.md#make_unique) の使用を検討してください。 オブジェクトのカスタム アロケーターを指定する必要がある場合、[allocate_shared](../standard-library/memory-functions.md#allocate_shared) を使用します。 オブジェクトでデリーターを引数として渡す方法がないため、カスタム デリーターが必要な場合に `make_shared` を使用することはできません。

次の例は、特定のコンストラクターのオーバーロードを呼び出して、型への共有ポインターを作成する方法を示しています。

### <a name="example"></a>例

```cpp
// stl_make_shared.cpp
// Compile by using: cl /W4 /EHsc stl_make_shared.cpp
#include <iostream>
#include <string>
#include <memory>
#include <vector>

class Song {
public:
   std::wstring title_;
   std::wstring artist_;

   Song(std::wstring title, std::wstring artist) : title_(title), artist_(artist) {}
   Song(std::wstring title) : title_(title), artist_(L"Unknown") {}
};

void CreateSharedPointers() {
   // Okay, but less efficient to have separate allocations for
   // Song object and shared_ptr control block.
   auto song = new Song(L"Ode to Joy", L"Beethoven");
   std::shared_ptr<Song> sp0(song);

   // Use make_shared function when possible. Memory for control block
   // and Song object are allocated in the same call:
   auto sp1 = std::make_shared<Song>(L"Yesterday", L"The Beatles");
   auto sp2 = std::make_shared<Song>(L"Blackbird", L"The Beatles");

   // make_shared infers which constructor to use based on the arguments.
   auto sp3 = std::make_shared<Song>(L"Greensleeves");

   // The playlist vector makes copies of the shared_ptr pointers.
   std::vector<std::shared_ptr<Song>> playlist;
   playlist.push_back(sp0);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   playlist.push_back(sp3);
   playlist.push_back(sp1);
   playlist.push_back(sp2);
   for (auto&& sp : playlist) {
      std::wcout << L"Playing " << sp->title_ <<
         L" by " << sp->artist_ << L", use count: " <<
         sp.use_count() << std::endl;
   }
}

int main() {
   CreateSharedPointers();
}
```

この例では、次の出力が生成されます:

```Output
Playing Ode to Joy by Beethoven, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
Playing Greensleeves by Unknown, use count: 2
Playing Yesterday by The Beatles, use count: 3
Playing Blackbird by The Beatles, use count: 3
```

## <a name="make_unique"></a>make_unique

指定した引数を使用して構築された、指定された型のオブジェクトへの [unique_ptr](../standard-library/unique-ptr-class.md) を作成して返します。

```cpp
// make_unique<T>
template <class T, class... Types>
    unique_ptr<T> make_unique(Types&&... Args)
    {
        return (unique_ptr<T>(new T(forward<Types>(Args)...)));
    }

// make_unique<T[]>
template <class T>
    make_unique(size_t Size)
    {
        return (unique_ptr<T>(new Elem[Size]()));
    }

// make_unique<T[N]> disallowed
template <class T, class... Types>
    typename enable_if<extent<T>::value != 0, void>::type make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>パラメーター

*\T*\
`unique_ptr` が指すオブジェクトの型。

*型*\
*Args*によって指定されたコンストラクター引数の型。

*Value*\
*T*型のオブジェクトのコンストラクターに渡される引数。

*Elem*\
*T*型の要素の配列。

*幅*\
新しい配列に領域を割り当てる要素の数。

### <a name="remarks"></a>Remarks

最初のオーバーロードは、1つのオブジェクトに対して使用され、2番目のオーバーロードは配列に対して呼び出されます。3番目の\<オーバーロードでは、型引数 (make_unique T [N] >) で配列のサイズを指定できません。この構築は現在のではサポートされていません。規格. `make_unique` を使用して、配列への `unique_ptr` を作成する場合、配列要素を個別に初期化する必要があります。 このオーバーロードを検討している場合、[std::vector](../standard-library/vector-class.md) の使用が適切である可能性があります。

`make_unique` は、例外セーフを目的として慎重に実装されるため、`make_unique` コンストラクターを直接呼び出す代わりに、`unique_ptr` を使用することをお勧めします。

### <a name="example"></a>例

次の例は、`make_unique` を使用する方法を示しています。 その他の例については、「[方法:Unique_ptr インスタンス](../cpp/how-to-create-and-use-unique-ptr-instances.md)を作成して使用します。

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

`unique_ptr` に関連してエラー C2280 が発生した場合、削除された関数であるコピー コンストラクターを呼び出そうとしたことが原因となっている可能性が高いです。

## <a name="owner_less"></a>owner_less

共有ポインターとウィーク ポインターの所有権ベースの混合型比較を実行します。 左のパラメーターがメンバー関数`owner_before`によって右のパラメーターの前に並べられている場合に true を返します。

```cpp
template <class Type>
    struct owner_less; // not defined

template <class Type>
struct owner_less<shared_ptr<Type>> {
    bool operator()(
    const shared_ptr<Type>& left,
    const shared_ptr<Type>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Type>& right);
};

template <class Type>
struct owner_less<weak_ptr<Type>>
    bool operator()(
    const weak_ptr<Type>& left,
    const weak_ptr<Type>& right);

    bool operator()(
    const weak_ptr<Type>& left,
    const shared_ptr<Ty>& right);

    bool operator()(
    const shared_ptr<Type>& left,
    const weak_ptr<Type>& right);
};
```

### <a name="parameters"></a>パラメーター

*左 (_r)* \
共有またはウィーク ポインター。

*そうです*\
共有またはウィーク ポインター。

### <a name="remarks"></a>Remarks

このテンプレート クラスは、すべてのメンバー演算子が `left.owner_before(right)` を返すように定義します。

## <a name="return_temporary_buffer"></a>return_temporary_buffer

`get_temporary_buffer` テンプレート関数を使用して割り当てられた一時メモリを解放します。

```cpp
template <class Type>
    void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>パラメーター

*_Pbuf*\
割り当てを解放するメモリへのポインター。

### <a name="remarks"></a>Remarks

この関数は、一時的なメモリにのみ使用する必要があります。

### <a name="example"></a>例

```cpp
// memory_ret_temp_buf.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

int main( )
{
   // Create an array of ints
   int intArray [ ] = { 10, 20, 30, 40, 100, 200, 300 };
   int count = sizeof ( intArray ) / sizeof ( int );
   cout << "The number of integers in the array is: "
         << count << "." << endl;

   pair<int *, ptrdiff_t> resultPair;
   resultPair = get_temporary_buffer<int>( count );

   cout << "The number of elements that the allocated memory\n"
         << " could store is given by: resultPair.second = "
         << resultPair.second << "." << endl;

   int* tempBuffer = resultPair.first;

   // Deallocates memory allocated with get_temporary_buffer
   return_temporary_buffer ( tempBuffer );
}
```

```Output
The number of integers in the array is: 7.
The number of elements that the allocated memory
could store is given by: resultPair.second = 7.
```

## <a name="static_pointer_cast"></a>static_pointer_cast

shared_ptr への静的なキャスト。

```cpp
template <class Ty, class Other>
    shared_ptr<Ty> static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

*~* \
返される共有ポインターによって制御される型。

*他の*\
引数の共有ポインターによって制御される型。

*他の*\
引数の共有ポインター。

### <a name="remarks"></a>Remarks

`sp`このテンプレート関数は、が空`shared_ptr`のオブジェクトの場合は空の shared_ptr オブジェクトを返します。それ以外の場合は、によって所有さ`sp`れているリソースを所有する[shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty > オブジェクトを返します。 式 `static_cast<Ty*>(sp.get())` は有効な式である必要があります。

### <a name="example"></a>例

```cpp
// std__memory__static_pointer_cast.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct base
{
    int val;
};

struct derived
    : public base
{
};

int main()
{
    std::shared_ptr<base> sp0(new derived);
    std::shared_ptr<derived> sp1 =
        std::static_pointer_cast<derived>(sp0);

    sp0->val = 3;
    std::cout << "sp1->val == " << sp1->val << std::endl;

    return (0);
}
```

```Output
sp1->val == 3
```

## <a name="swap"></a>フォト

2 つの shared_ptr オブジェクトまたは weak_ptr オブジェクトをスワップします。

```cpp
template <class Ty, class Other>
    void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
    void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>パラメーター

*~* \
左辺の共有/ウィーク ポインターによって制御される型。

*他の*\
右辺の共有/ウィーク ポインターによって制御される型。

*左側*\
左辺の共有/ウィーク ポインター。

*そうです*\
右辺の共有/ウィーク ポインター。

### <a name="remarks"></a>Remarks

このテンプレート関数は、`left.swap(right)` を呼び出します。

### <a name="example"></a>例

```cpp
// std__memory__swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="undeclare_no_pointers"></a>undeclare_no_pointers

ベース アドレス ポインターとブロック サイズで定義されたメモリ ブロック内の文字が、追跡可能なポインターを含む可能性があることをガベージ コレクターに通知します。

```cpp
void undeclare_no_pointers(char* ptr, size_t _Size);
```

### <a name="remarks"></a>Remarks

関数は、アドレス`[ptr, ptr + _Size)`の範囲に追跡可能なポインターが含まれている可能性があることをガベージコレクターに通知します。

## <a name="undeclare_reachable"></a>undeclare_reachable

指定したメモリ位置の到達可能性の宣言を取り消します。

```cpp
template <class Type>
    Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>パラメーター

*ポインター*\
到達不可と宣言されるメモリ アドレスへのポインター。

### <a name="remarks"></a>Remarks

*Ptr*が**nullptr**でない場合、関数は、 *ptr*に到達できなくなったことをガベージコレクターに通知します。 これは、 *ptr*と等しいことを比較する、安全に派生したポインターを返します。

## <a name="uninitialized_copy"></a>uninitialized_copy

指定されたソース範囲にあるオブジェクトを、初期化されていないターゲット範囲にコピーします。

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>パラメーター

*まずは*\
ソース範囲内の先頭の要素を示す入力反復子。

*前の*\
ソース範囲内の最後の要素を示す入力反復子。

*先*\
ターゲット範囲内の先頭の要素を示す前方反復子。

### <a name="return-value"></a>戻り値

ソース範囲が空の場合を除き、ターゲット範囲を超える最初の位置を示す前方反復子。

### <a name="remarks"></a>Remarks

このアルゴリズムによって、オブジェクトの構築からメモリの割り当てを分離できます。

このテンプレート関数は、実質的に次の内容を実行します。

```cpp
while (first != last) {
    new (static_cast<void*>(&* dest++))
        typename iterator_traits<InputIterator>::value_type(*first++);
}
return dest;
```

ただし、このコードが例外をスローする場合を除きます。 この場合は、構築されたオブジェクトはすべて破棄され、再度例外がスローされます。

### <a name="example"></a>例

```cpp
// memory_uninit_copy.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer
{
public:
    Integer(int x) : val(x) {}
    int get() { return val; }
private:
    int val;
};

int main()
{
    int Array[] = { 10, 20, 30, 40 };
    const int N = sizeof(Array) / sizeof(int);

    int i;
    cout << "The initialized Array contains " << N << " elements: ";
    for (i = 0; i < N; i++)
    {
        cout << " " << Array[i];
    }
    cout << endl;

    Integer* ArrayPtr = (Integer*)malloc(N * sizeof(int));
    Integer* LArrayPtr = uninitialized_copy(
        Array, Array + N, ArrayPtr);  // C4996

    cout << "Address of position after the last element in the array is: "
        << &Array[0] + N << endl;
    cout << "The iterator returned by uninitialized_copy addresses: "
        << (void*)LArrayPtr << endl;
    cout << "The address just beyond the last copied element is: "
        << (void*)(ArrayPtr + N) << endl;

    if ((&Array[0] + N) == (void*)LArrayPtr)
        cout << "The return value is an iterator "
        << "pointing just beyond the original array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the original array." << endl;

    if ((void*)LArrayPtr == (void*)(ArrayPtr + N))
        cout << "The return value is an iterator "
        << "pointing just beyond the copied array." << endl;
    else
        cout << "The return value is an iterator "
        << "not pointing just beyond the copied array." << endl;

    free(ArrayPtr);

    cout << "Note that the exact addresses returned will vary\n"
        << "with the memory allocation in individual computers."
        << endl;
}
```

## <a name="uninitialized_copy_n"></a>uninitialized_copy_n

入力反復子から、指定した数の要素のコピーを作成します。 コピーは前方反復子に格納されます。

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>パラメーター

*まずは*\
コピーするオブジェクトを参照する入力反復子。

*数*\
オブジェクトをコピーする回数を指定する符号付きまたは符号なし整数型。

*先*\
新しいコピー先を参照する前方反復子。

### <a name="return-value"></a>戻り値

ターゲットを超えた最初の位置を示す前方反復子。 ソース範囲が空の場合、反復子は*最初*にアドレスを指定します。

### <a name="remarks"></a>Remarks

このテンプレート関数は、実質的に次の内容を実行します。

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

ただし、このコードが例外をスローする場合を除きます。 この場合は、構築されたオブジェクトはすべて破棄され、再度例外がスローされます。

## <a name="uninitialized_default_construct"></a>uninitialized_default_construct

```cpp
template <class ForwardIterator>
    void uninitialized_default_construct(ForwardIterator first, ForwardIterator last); 
```

### <a name="remarks"></a>Remarks

次と同じ:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type;
```

## <a name="uninitialized_default_construct_n"></a>uninitialized_default_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_default_construct_n(ForwardIterator first, Size n)
```

### <a name="remarks"></a>Remarks

次と同じ:

```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type; return first;
```

## <a name="uninitialized_fill"></a>uninitialized_fill

指定された値のオブジェクトを、初期化されていないコピー先の範囲にコピーします。

```cpp
template <class ForwardIterator, class Type>
    void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>パラメーター

*まずは*\
初期化されるターゲット範囲内の先頭の要素を示す前方反復子。

*前の*\
初期化されるターゲット範囲内の末尾の要素を示す前方反復子。

*val*\
ターゲット範囲を初期化するために使用される値。

### <a name="remarks"></a>Remarks

このアルゴリズムによって、オブジェクトの構築からメモリの割り当てを分離できます。

このテンプレート関数は、実質的に次の内容を実行します。

```cpp
while (first != last)
    new (static_cast<void*>(&* first ++))
        typename iterator_traits<ForwardIterator>::value_type (val);
```

ただし、このコードが例外をスローする場合を除きます。 この場合は、構築されたオブジェクトはすべて破棄され、再度例外がスローされます。

### <a name="example"></a>例

```cpp
// memory_uninit_fill.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

class Integer {         // No default constructor
   public:
      Integer( int x ) : val( x ) {}
      int get( ) { return val; }
   private:
      int val;
};

int main( )
{
   const int N = 10;
   Integer val ( 25 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill( Array, Array + N, val );
   int i;
   cout << "The initialized Array contains: ";
      for ( i = 0 ; i < N; i++ )
      {
         cout << Array [ i ].get( ) << " ";
      }
   cout << endl;
}
```

```Output
The initialized Array contains: 25 25 25 25 25 25 25 25 25 25
```

## <a name="uninitialized_fill_n"></a>uninitialized_fill_n

指定された値のオブジェクトを、初期化されていないターゲット範囲にある指定された数の要素にコピーします。

```cpp
template <class FwdIt, class Size, class Type>
    void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>パラメーター

*まずは*\
初期化されるターゲット範囲内の先頭の要素を示す前方反復子。

*数*\
初期化される要素の数。

*val*\
ターゲット範囲を初期化するために使用される値。

### <a name="remarks"></a>Remarks

このアルゴリズムによって、オブジェクトの構築からメモリの割り当てを分離できます。

このテンプレート関数は、実質的に次の内容を実行します。

```cpp
while (0 < count--)
    new (static_cast<void*>(&* first++))
        typename iterator_traits<ForwardIterator>::value_type(val);
```

ただし、このコードが例外をスローする場合を除きます。 この場合は、構築されたオブジェクトはすべて破棄され、再度例外がスローされます。

### <a name="example"></a>例

```cpp
// memory_uninit_fill_n.cpp
// compile with: /EHsc /W3
#include <memory>
#include <iostream>

using namespace std;

class Integer {   // No default constructor
public:
   Integer( int x ) : val( x ) {}
   int get( ) { return val; }
private:
   int val;
};

int main() {
   const int N = 10;
   Integer val ( 60 );
   Integer* Array = ( Integer* ) malloc( N * sizeof( int ) );
   uninitialized_fill_n( Array, N, val );  // C4996
   int i;
   cout << "The uninitialized Array contains: ";
   for ( i = 0 ; i < N; i++ )
      cout << Array [ i ].get( ) <<  " ";
}
```

## <a name="uninitialized_move"></a>uninitialized_move

```cpp
template <class InputIterator, class ForwardIterator>
    ForwardIterator uninitialized_move(InputIterator first, InputIterator last, ForwardIterator result); 
```

### <a name="remarks"></a>Remarks

次と同じ:

```cpp
for (; first != last; (void)++result, ++first)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); 
        return result;
```

例外がスローされた場合、範囲内の一部のオブジェクトが有効であるが指定されていない状態のままになることがあります。

## <a name="uninitialized_move_n"></a>uninitialized_move_n

```cpp
template <class InputIterator, class Size, class ForwardIterator>
    pair<InputIterator, ForwardIterator> uninitialized_move_n(InputIterator first, Size n, ForwardIterator result);
```

### <a name="remarks"></a>Remarks

次と同じ:

```cpp
for (; n > 0; ++result, (void) ++first, --n)
    ::new (static_cast<void*>(addressof(*result)))
        typename iterator_traits<ForwardIterator>::value_type(std::move(*first)); return {first,result};
```

例外がスローされた場合、範囲内の一部のオブジェクトが有効であるが指定されていない状態のままになることがあります。

## <a name="uninitialized_value_construct"></a>uninitialized_value_construct

```cpp
template <class ForwardIterator>
    void uninitialized_value_construct(ForwardIterator first, ForwardIterator last);
```

### <a name="remarks"></a>Remarks

次と同じ:

```cpp
for (; first != last; ++first)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type();
```

## <a name="uninitialized_value_construct_n"></a>uninitialized_value_construct_n

```cpp
template <class ForwardIterator, class Size>
    ForwardIterator uninitialized_value_construct_n(ForwardIterator first, Size n);
```

次と同じ:
```cpp
for (; n>0; (void)++first, --n)
    ::new (static_cast<void*>(addressof(*first)))
        typename iterator_traits<ForwardIterator>::value_type(); return first;
```

## <a name="uses_allocator_v"></a>uses_allocator_v

```cpp
template <class T, class Alloc>
    inline constexpr bool uses_allocator_v = uses_allocator<T, Alloc>::value;
```

## <a name="see-also"></a>関連項目

[\<memory>](../standard-library/memory.md)
