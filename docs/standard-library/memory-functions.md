---
title: '&lt;memory&gt; 関数'
ms.date: 11/04/2016
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
ms.openlocfilehash: 2b7f65e2bca728ccde50cdee503f920291aa3ee4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619064"
---
# <a name="ltmemorygt-functions"></a>&lt;memory&gt; 関数

||||
|-|-|-|
|[addressof](#addressof)|[align](#align)|[allocate_shared](#allocate_shared)|
|[const_pointer_cast](#const_pointer_cast)|[declare_no_pointers](#declare_no_pointers)|[declare_reachable](#declare_reachable)|
|[default_delete](#default_delete)|[dynamic_pointer_cast](#dynamic_pointer_cast)|[get_deleter](#get_deleter)|
|[get_pointer_safety](#get_pointer_safety)|[get_temporary_buffer](#get_temporary_buffer)|[make_shared](#make_shared)|
|[make_unique](#make_unique)|[owner_less](#owner_less)|[return_temporary_buffer](#return_temporary_buffer)|
|[static_pointer_cast](#static_pointer_cast)|[swap (C++ 標準ライブラリ)](#swap)|[undeclare_no_pointers](#undeclare_no_pointers)|
|[undeclare_reachable](#undeclare_reachable)|[uninitialized_copy](#uninitialized_copy)|[uninitialized_copy_n](#uninitialized_copy_n)|
|[uninitialized_fill](#uninitialized_fill)|[uninitialized_fill_n](#uninitialized_fill_n)|

## <a name="addressof"></a>  addressof

オブジェクトの実際のアドレスを取得します。

```cpp
template <class T>
T* addressof(T& Val);
```

### <a name="parameters"></a>パラメーター

*val*<br/>
実際のアドレスを取得する対象のオブジェクトまたは関数。

### <a name="return-value"></a>戻り値

オブジェクトまたは関数によって参照される実際のアドレス*Val*、オーバー ロードされた場合でも、`operator&()`存在します。

### <a name="remarks"></a>Remarks

## <a name="align"></a>  align

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

*アラインメント*<br/>
試行するアラインメントの境界。

*Size*<br/>
アラインされたストレージのサイズ (バイト単位)。

*ptr*<br/>
使用する利用可能な一連の記憶域プールの開始アドレス。 このパラメーターは、出力パラメーターでも、配置が成功した場合、新しい開始アドレスに設定されます。 `align()` が失敗した場合、このパラメーターは変更されません。

*スペース*<br/>
アラインされた記憶域の作成に使用する `align()` で利用可能な合計領域。 このパラメーターは出力パラメーターでもあり、アラインされたストレージと関連するオーバーヘッドが差し引かれた後の記憶域バッファーに残されている調整された領域を格納します。

`align()` が失敗した場合、このパラメーターは変更されません。

### <a name="return-value"></a>戻り値

要求されたアライン バッファー使用可能な領域以外にも適合しない場合は null ポインターそれ以外の場合の新しい値*Ptr*します。

### <a name="remarks"></a>Remarks

変更された*Ptr*と*領域*パラメーターを使用すると、呼び出す`align()`場合によっては異なる値で、同じバッファーについて繰り返し*配置*と*サイズ*します。 `align()` の使用方法の 1 つを次のコード スニペットに示します。

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

## <a name="allocate_shared"></a>  allocate_shared

指定されたアロケーターを使用することによって、特定の型に割り当てられ構築されたオブジェクトに対して `shared_ptr` を作成します。 `shared_ptr` を返します。

```cpp
template <class Type, class Allocator, class... Types>
shared_ptr<Type>
allocate_shared(Allocator Alloc, Types&&... Args);
```

### <a name="parameters"></a>パラメーター

*Alloc*<br/>
オブジェクトを作成するために使用されるアロケーター。

*Args*<br/>
オブジェクトになるゼロ個以上の引数。

### <a name="remarks"></a>Remarks

関数は、オブジェクトを作成します。 `shared_ptr<Type>`、へのポインター`Type(Args...)`として割り当てられ、構築された*アロケーション*します。

## <a name="const_pointer_cast"></a>  const_pointer_cast

shared_ptr への const キャスト。

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
const_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
返される共有ポインターによって制御される型。

*その他*<br/>
引数の共有ポインターによって制御される型。

*その他*<br/>
引数の共有ポインター。

### <a name="remarks"></a>Remarks

場合、テンプレート関数は空の shared_ptr オブジェクトを返します`const_cast<Ty*>(sp.get())`; null ポインターを返しますそれ以外の場合を返します、 [shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty > によって所有されているリソースを所有するオブジェクト`sp`します。 式 `const_cast<Ty*>(sp.get())` は有効な式である必要があります。

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

## <a name="declare_no_pointers"></a>  declare_no_pointers

ベース アドレス ポインターとブロック サイズで定義されたメモリ ブロック内の文字に追跡可能なポインターが含まれていないことを、ガベージ コレクターに通知します。

```cpp
void declare_no_pointers(
    char* ptr,
    size_t _Size);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ptr*|追跡可能なポインターがもう含まれない最初の文字のアドレス。|
|*サイズ) (_s*|開始されるブロックのサイズ*ptr*追跡可能なポインターが含まれていません。|

### <a name="remarks"></a>Remarks

関数は、ガベージ コレクターに通知するアドレスの範囲`[ ptr, ptr + _Size)`追跡可能なポインターを含まない。 (割り当て済み記憶域へのポインターする必要がありますが逆参照されないに到達可能な場合を除き、します。)

## <a name="declare_reachable"></a>  declare_reachable

指定されたアドレスが、割り当てられたストレージのアドレスであり、そのストレージに到達可能であることをガベージ コレクションに通知します。

```cpp
void declare_reachable(void* ptr);
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
到達可能な割り当て済みの有効なストレージ領域へのポインター。

### <a name="remarks"></a>Remarks

場合*ptr*が null でない関数は、ガベージ コレクターに通知する*ptr*がこれ以降到達可能な (有効な割り当て済み記憶域を指します)。

## <a name="default_delete"></a>  default_delete

割り当てられたオブジェクトを削除します。**演算子 new**します。 `unique_ptr` での使用に適しています。

```cpp
struct default_delete {
   constexpr default_delete() noexcept = default;
   template <class Other, class = typename enable_if<is_convertible<Other*, T*>::value, void>::type>>
   default_delete(const default_delete<Other>&) noexcept;
   void operator()(T* Ptr) const noexcept;
};
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
削除するオブジェクトへのポインター。

*その他*<br/>
削除対象の配列内の要素の型。

### <a name="remarks"></a>Remarks

テンプレート クラスについて説明します、`deleter`で割り当てられたスカラー オブジェクトを削除する**演算子 new**テンプレート クラスの使用に適した、`unique_ptr`します。 明示的な特殊化 `default_delete<Type[]>` もあります。

## <a name="dynamic_pointer_cast"></a>  dynamic_pointer_cast

shared_ptr への動的なキャストを実行します。

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
dynamic_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
返される共有ポインターによって制御される型。

*その他*<br/>
引数の共有ポインターによって制御される型。

*sp*<br/>
引数の共有ポインター。

### <a name="remarks"></a>Remarks

場合、テンプレート関数は空の shared_ptr オブジェクトを返します`dynamic_cast<Ty*>(sp.get())`; null ポインターを返しますそれ以外の場合を返します、 [shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty > によって所有されているリソースを所有するオブジェクト*sp*. 式 `dynamic_cast<Ty*>(sp.get())` は有効な式である必要があります。

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

## <a name="get_deleter"></a>  get_deleter

shared_ptr から削除子を取得します。

```cpp
template <class D, class Ty>
D* get_deleter(const shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>パラメーター

*D*<br/>
削除子の型。

*Ty*<br/>
共有ポインターによって制御される型。

*sp*<br/>
共有ポインター。

### <a name="remarks"></a>Remarks

テンプレート関数は、型の削除子へのポインターを返します*D*に属している、 [shared_ptr クラス](../standard-library/shared-ptr-class.md)オブジェクト*sp*します。 場合*sp*子を持たない型の削除子がない場合または*D* 0 を返します。

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

## <a name="get_pointer_safety"></a>  get_pointer_safety

ガベージ コレクターが想定するポインターの安全性の種類を返します。

```cpp
pointer_safety get_pointer_safety();
```

### <a name="remarks"></a>Remarks

関数は、自動ガベージ コレクターが想定ポインターの安全性の種類を返します。

## <a name="get_temporary_buffer"></a>  get_temporary_buffer

指定した要素数を上限とする要素シーケンスに対し、一時的なストレージを割り当てます。

```cpp
template <class Type>
pair<Type *, ptrdiff_t> get_temporary_buffer(ptrdiff_t count);
```

### <a name="parameters"></a>パラメーター

*count*<br/>
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

## <a name="make_shared"></a>  make_shared

既定のアロケーターを使用してゼロ以上の引数から構築された割り当て済みオブジェクトを指し示す `shared_ptr` を作成し、返します。 指定された型のオブジェクトおよび `shared_ptr` の両方を割り当て構築することでオブジェクトの共有所有権を管理し、`shared_ptr` を返します.

```cpp
template <class Type, class... Types>
shared_ptr<Type>
make_shared(Types&&... _Args);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Args*|0 個以上のコンス トラクター引数。 関数は、提供された引数に基づいてどのコンストラクターのオーバーロードを呼び出すかを推測します。|

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

## <a name="make_unique"></a>  make_unique

指定した引数を使用して構築された、指定された型のオブジェクトへの [unique_ptr](../standard-library/unique-ptr-class.md) を作成して返します。

```cpp
// make_unique<T>
template <class T, class... Types>
unique_ptr<T>
make_unique(Types&&... Args)
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
typename enable_if<extent<T>::value != 0, void>::type
make_unique(Types&&...) = delete;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`unique_ptr` が指すオブジェクトの型。

*型*<br/>
指定されたコンス トラクター引数の型*Args*します。

*Args*<br/>
型のオブジェクトのコンス トラクターに渡される引数*T*します。

*Elem*<br/>
型の要素の配列*T*します。

*Size*<br/>
新しい配列に領域を割り当てる要素の数。

### <a name="remarks"></a>Remarks

最初のオーバーロードは、単一オブジェクトに対して使用されます。2 番目のオーバーロードは、配列に対して呼び出されます。3 番目のオーバーロードは、ユーザーが型引数 (make_unique\<T[N]>) で配列のサイズを指定することを防ぎます。この構造は、現在の標準ではサポートされていません。 `make_unique` を使用して、配列への `unique_ptr` を作成する場合、配列要素を個別に初期化する必要があります。 このオーバーロードを検討している場合、[std::vector](../standard-library/vector-class.md) の使用が適切である可能性があります。

`make_unique` は、例外セーフを目的として慎重に実装されるため、`make_unique` コンストラクターを直接呼び出す代わりに、`unique_ptr` を使用することをお勧めします。

### <a name="example"></a>例

次の例は、`make_unique` を使用する方法を示しています。 その他の例については、「[方法: unique_ptr インスタンスを作成して使用する](../cpp/how-to-create-and-use-unique-ptr-instances.md)」を参照してください。

[!code-cpp[stl_smart_pointers#214](../cpp/codesnippet/CPP/memory-functions_1.cpp)]

`unique_ptr` に関連してエラー C2280 が発生した場合、削除された関数であるコピー コンストラクターを呼び出そうとしたことが原因となっている可能性が高いです。

## <a name="owner_less"></a>  owner_less

共有ポインターとウィーク ポインターの所有権ベースの混合型比較を実行します。 返します**true** left パラメーターがメンバー関数によって適切なパラメーターの前に順序付けられたかどうか`owner_before`します。

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

*_ 左*<br/>
共有またはウィーク ポインター。

*right*<br/>
共有またはウィーク ポインター。

### <a name="remarks"></a>Remarks

このテンプレート クラスは、すべてのメンバー演算子が `left.owner_before(right)` を返すように定義します。

## <a name="return_temporary_buffer"></a>  return_temporary_buffer

`get_temporary_buffer` テンプレート関数を使用して割り当てられた一時メモリを解放します。

```cpp
template <class Type>
void return_temporary_buffer(Type* _Pbuf);
```

### <a name="parameters"></a>パラメーター

*_Pbuf*<br/>
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

## <a name="static_pointer_cast"></a>  static_pointer_cast

shared_ptr への静的なキャスト。

```cpp
template <class Ty, class Other>
shared_ptr<Ty>
static_pointer_cast(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
返される共有ポインターによって制御される型。

*その他*<br/>
引数の共有ポインターによって制御される型。

*その他*<br/>
引数の共有ポインター。

### <a name="remarks"></a>Remarks

場合、テンプレート関数は空の shared_ptr オブジェクトを返します`sp`は、空`shared_ptr`以外のオブジェクトを返しますそれ以外の場合、 [shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty >によって所有されているリソースを所有するオブジェクト`sp`. 式 `static_cast<Ty*>(sp.get())` は有効な式である必要があります。

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

## <a name="swap"></a>  swap (C++ 標準ライブラリ)

2 つの shared_ptr オブジェクトまたは weak_ptr オブジェクトをスワップします。

```cpp
template <class Ty, class Other>
void swap(shared_ptr<Ty>& left, shared_ptr<Other>& right);

template <class Ty, class Other>
void swap(weak_ptr<Ty>& left, weak_ptr<Other>& right);
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
左辺の共有/ウィーク ポインターによって制御される型。

*その他*<br/>
右辺の共有/ウィーク ポインターによって制御される型。

*left*<br/>
左辺の共有/ウィーク ポインター。

*right*<br/>
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

## <a name="undeclare_no_pointers"></a>  undeclare_no_pointers

ベース アドレス ポインターとブロック サイズで定義されたメモリ ブロック内の文字が、追跡可能なポインターを含む可能性があることをガベージ コレクターに通知します。

```cpp
void undeclare_no_pointers(
    char* ptr,
    size_t _Size);
```

### <a name="remarks"></a>Remarks

関数は、ガベージ コレクターに通知するアドレスの範囲`[ptr, ptr + _Size)`追跡可能なポインターを含めるようになりましたことができます。

## <a name="undeclare_reachable"></a>  undeclare_reachable

指定されたメモリ位置の到達可能性の宣言を取り消します。

```cpp
template <class Type>
Type *undeclare_reachable(Type* ptr);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ptr*|到達不可と宣言されるメモリ アドレスへのポインター。|

### <a name="remarks"></a>Remarks

場合*ptr*ない**nullptr**、関数は、ガベージ コレクターに通知する*ptr*に到達できなくします。 等しいとを比較する安全に派生したポインターを返す*ptr*します。

## <a name="uninitialized_copy"></a>  uninitialized_copy

指定されたソース範囲にあるオブジェクトを、初期化されていないターゲット範囲にコピーします。

```cpp
template <class InputIterator, class ForwardIterator>
ForwardIterator uninitialized_copy(InputIterator first, InputIterator last, ForwardIterator dest);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
ソース範囲内の先頭の要素を示す入力反復子。

*last*<br/>
ソース範囲内の最後の要素を示す入力反復子。

*dest*<br/>
ターゲット範囲内の先頭の要素を示す前方反復子。

### <a name="return-value"></a>戻り値

ソース範囲が空であった場合を除き、先の範囲を超える最初の位置を示す前方反復子。

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

## <a name="uninitialized_copy_n"></a>  uninitialized_copy_n

入力反復子から、指定した数の要素のコピーを作成します。 コピーは前方反復子に格納されます。

```cpp
template <class InputIterator, class Size, class ForwardIterator>
ForwardIterator uninitialized_copy_n(
    InputIterator first,
    Size count,
    ForwardIterator dest);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
コピーするオブジェクトを参照する入力反復子。

*count*<br/>
オブジェクトをコピーする回数を指定する符号付きまたは符号なし整数型。

*dest*<br/>
新しいコピー先を参照する前方反復子。

### <a name="return-value"></a>戻り値

ターゲットを超えた最初の位置を示す前方反復子。 ソース範囲が空であった場合、反復*最初*します。

### <a name="remarks"></a>Remarks

このテンプレート関数は、実質的に次の内容を実行します。

```cpp
    for (; 0 < count; --count)
        new (static_cast<void*>(&* dest++))
            typename iterator_traits<InputIterator>::value_type(*first++);
    return dest;
```

ただし、このコードが例外をスローする場合を除きます。 この場合は、構築されたオブジェクトはすべて破棄され、再度例外がスローされます。

## <a name="uninitialized_fill"></a>  uninitialized_fill

指定された値のオブジェクトを、初期化されていないコピー先の範囲にコピーします。

```cpp
template <class ForwardIterator, class Type>
void uninitialized_fill(ForwardIterator first, ForwardIterator last, const Type& val);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
初期化されるターゲット範囲内の先頭の要素を示す前方反復子。

*last*<br/>
初期化されるターゲット範囲内の末尾の要素を示す前方反復子。

*val*<br/>
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

## <a name="uninitialized_fill_n"></a>  uninitialized_fill_n

指定された値のオブジェクトを、初期化されていないターゲット範囲にある指定された数の要素にコピーします。

```cpp
template <class FwdIt, class Size, class Type>
void uninitialized_fill_n(ForwardIterator first, Size count, const Type& val);
```

### <a name="parameters"></a>パラメーター

*first*<br/>
初期化されるターゲット範囲内の先頭の要素を示す前方反復子。

*count*<br/>
初期化される要素の数。

*val*<br/>
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

## <a name="see-also"></a>関連項目

[\<memory>](../standard-library/memory.md)<br/>
