---
title: auto_ptr クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
helpviewer_keywords:
- std::auto_ptr [C++]
- std::auto_ptr [C++], element_type
- std::auto_ptr [C++], get
- std::auto_ptr [C++], release
- std::auto_ptr [C++], reset
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
ms.openlocfilehash: 14841662235f075d74120673208dd54531763c09
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456713"
---
# <a name="autoptr-class"></a>auto_ptr クラス

コントロールがあるブロックを離れるときに確実にリソースが自動的に破棄されるように、リソースの周囲にスマート ポインターをラップします。

より高機能なこの `unique_ptr` クラスは `auto_ptr` に代わるものです。 詳細については、「[unique_ptr クラス](../standard-library/unique-ptr-class.md)」をご覧ください。

`throw()` および例外処理の詳細については、「[例外の仕様 (スロー)](../cpp/exception-specifications-throw-cpp.md)」をご覧ください。

## <a name="syntax"></a>構文

```cpp
class auto_ptr {
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```

### <a name="parameters"></a>パラメーター

*そうです*\
既存のリソースの取得元となる `auto_ptr`。

*ポインター*\
格納されたポインターを置換するように指定されたポインター。

## <a name="remarks"></a>Remarks

このテンプレートクラスは、割り当てられたオブジェクト`auto_ptr`に対すると呼ばれるスマートポインターを記述します。 ポインターは、null であるか、または**new**によって割り当てられたオブジェクトを指定している必要があります。 `auto_ptr` は、格納されている値が別のオブジェクトに割り当てられている場合、所有権を転送します。 (転送後、格納されている値は null ポインターに置換されます。)`auto_ptr<Type>` のデストラクターが割り当てられたオブジェクトを削除します。 `auto_ptr<Type>` は、コントロールがブロックを離れるとき、例外がスローされる場合であっても、割り当てられたオブジェクトが確実に自動的に削除するようにします。 同じオブジェクトを所有する 2 つの `auto_ptr<Type>` オブジェクトを構成しないでください。

`auto_ptr<Type>` オブジェクトを関数呼び出しの引数として値渡しで渡せます。 `auto_ptr` を標準ライブラリのコンテナーの要素にすることはできません。 C++ 標準ライブラリのコンテナーを持つ `auto_ptr<Type>` オブジェクトのシーケンスを確実に管理することはできません。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|||
|-|-|
|[auto_ptr](#auto_ptr)|`auto_ptr` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedef

|||
|-|-|
|[element_type](#element_type)|この型は、テンプレート パラメーター `Type` のシノニムです。|

### <a name="functions"></a>関数

|||
|-|-|
|[get](#get)|このメンバー関数は、格納されているポインター `myptr` を返します。|
|[release](#release)|このメンバーは、格納されたポインター `myptr` を null ポインターで置換して、以前に格納されたポインターを返します。|
|[reset](#reset)|このメンバー関数は、関数呼び出しの結果として格納されているポインター値 `myptr` が変化する場合に限り、式 `delete myptr` を評価します。 その後、格納されたポインターを *ptr* で置換します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[operator=](#op_eq)|1 つの `auto_ptr` オブジェクトから別のオブジェクトに所有権を転送する代入演算子。|
|[operator*](#op_star)|`auto_ptr` 型のオブジェクトの逆参照演算子。|
|[operator->](#op_arrow)|メンバーにアクセスできるようにする演算子。|
|[operator auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|1 つの種類の `auto_ptr` から別の種類の `auto_ptr` にキャストします。|
|[operator auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|`auto_ptr` から `auto_ptr_ref` にキャストします。|

### <a name="auto_ptr"></a>auto_ptr

`auto_ptr` 型のオブジェクトのコンストラクター。

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

#### <a name="parameters"></a>パラメーター

*ポインター*\
`auto_ptr` がカプセル化するオブジェクトへのポインター。

*そうです*\
コンストラクターによってコピーされる `auto_ptr` オブジェクト。

#### <a name="remarks"></a>Remarks

1つ目のコンストラクターは`myptr`、割り当てられたオブジェクトへの格納されたポインターである ptr を格納します。 2番目のコンストラクターは、 *right に格納*されているポインターの所有権を転送し*ます。* [](#release)での`myptr`リリース。

3番目のコンストラクターは、を格納`right`する点を除いて、2番目のコンストラクターと同じように動作します。 `ref`。 `release`で`myptr`は`ref` 、はに`right`格納されている参照です。

へのポインター `Other`をへの`Type`ポインターに暗黙的に変換できる場合、テンプレートコンストラクターは2番目のコンストラクターと同じように動作します。

#### <a name="example"></a>例

```cpp
// auto_ptr_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

void function ( auto_ptr<Int> &pi )
{
   ++( *pi );
   auto_ptr<Int> pi2( pi );
   ++( *pi2 );
   pi = pi2;
}

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   cout << pi->x << endl;
   function( pi );
   cout << pi->x << endl;
}
```

```Output
Constructing 00311AF8
5
7
Destructing 00311AF8
```

### <a name="element_type"></a>element_type

この型は、テンプレート パラメーター `Type` のシノニムです。

```cpp
typedef Type element  _type;
```

### <a name="get"></a>取得

このメンバー関数は、格納されているポインター `myptr` を返します。

```cpp
Type *get() const throw();
```

#### <a name="return-value"></a>戻り値

格納され`myptr`ているポインター。

#### <a name="example"></a>例

```cpp
// auto_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      x = i;
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;
   };

   int x;

};

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   pi.reset( new Int( 6 ) );
   Int* pi2 = pi.get ( );
   Int* pi3 = pi.release ( );
   if (pi2 == pi3)
      cout << "pi2 == pi3" << endl;
   delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="op_eq"></a>operator =

1 つの `auto_ptr` オブジェクトから別のオブジェクトに所有権を転送する代入演算子。

```cpp
template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

#### <a name="parameters"></a>パラメーター

*そうです*\
`auto_ptr` 型のオブジェクト。

#### <a name="return-value"></a>戻り値

`auto_ptr<Type>` 型のオブジェクトへの参照。

#### <a name="remarks"></a>Remarks

代入は式`delete myptr`を評価しますが、代入の結果`myptr`として格納されたポインターが変化する場合に限ります。 次に、 *right に格納*されているポインターの所有権を転送し*ます。* [](#release)での`myptr`リリース。 関数は __\*this__ を返します。

#### <a name="example"></a>例

メンバー演算子の使用例については、「 [auto_ptr](#auto_ptr)」を参照してください。

### <a name="op_star"></a>operator

`auto_ptr` 型のオブジェクトの逆参照演算子。

```cpp
Type& operator*() const throw();
```

#### <a name="return-value"></a>戻り値

ポインターが所有する型`Type`のオブジェクトへの参照。

#### <a name="remarks"></a>Remarks

間接演算子は `*`[get](#get) を返します。 つまり、格納されたポインターは、null にすることはできません。

#### <a name="example"></a>例

メンバー関数の使用例については、「 [auto_ptr](#auto_ptr)」を参照してください。

### <a name="op_arrow"></a>operator&gt;

メンバーにアクセスできるようにする演算子。

```cpp
Type * operator->() const throw();
```

#### <a name="return-value"></a>戻り値

を所有する`auto_ptr`オブジェクトのメンバー。

#### <a name="remarks"></a>Remarks

選択演算子は [get](#get)`( )` を返して、式 *ap*-> **member** が ( *ap*. **get**( ) )-> **member** と同じ動作をするようにします。ここで、*ap* はクラス `auto_ptr`\< **Type**> のオブジェクトです。 したがって、格納されているポインターは null `Type`にすることはできず、 `member`メンバーを持つクラス、構造体、または共用体型にする必要があります。

#### <a name="example"></a>例

メンバー関数の使用例については、「 [auto_ptr](#auto_ptr)」を参照してください。

### <a name="op_auto_ptr_lt_other_gt"></a>演算子 auto_ptr&lt;Other&gt;

1 つの種類の `auto_ptr` から別の種類の `auto_ptr` にキャストします。

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

#### <a name="return-value"></a>戻り値

型キャスト演算子は `auto_ptr` \< **Other**>( **\*this**) を返します。

#### <a name="example"></a>例

```cpp
// auto_ptr_op_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;
int main()
{
   auto_ptr<int> pi ( new int( 5 ) );
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;
}
```

### <a name="op_auto_ptr_ref_lt_other_gt"></a>演算子 auto_ptr_ref&lt;Other&gt;

`auto_ptr` から `auto_ptr_ref` にキャストします。

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

#### <a name="return-value"></a>戻り値

型キャスト演算子は **auto_ptr_ref**\< **Other**>( **\*this**) を返します。

#### <a name="example"></a>例

```cpp
// auto_ptr_op_auto_ptr_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer
    // f(ciap);
    f(iap); // compiles, but gives up ownership of pointer

            // here, iap owns a destroyed pointer so the following is bad:
            // *iap = 5; // BOOM

    cout << "main exiting\n";
}
```

```Output
~C:  2
main exiting
~C:  1
```

### <a name="release"></a>解除

このメンバーは、格納されたポインター `myptr` を null ポインターで置換して、以前に格納されたポインターを返します。

```cpp
Type *release() throw();
```

#### <a name="return-value"></a>戻り値

以前に格納されたポインター。

#### <a name="remarks"></a>Remarks

このメンバーは、格納されたポインター `myptr` を null ポインターで置換して、以前に格納されたポインターを返します。

#### <a name="example"></a>例

```cpp
// auto_ptr_release.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="reset"></a>解除

このメンバー関数は、式`delete myptr`を評価しますが、格納さ`myptr`れているポインター値が関数呼び出しの結果として変更された場合に限ります。 その後、格納されたポインターを `ptr` で置換します。

```cpp
void reset(Type* ptr = 0);
```

#### <a name="parameters"></a>パラメーター

*ポインター*\
格納されているポインター `myptr`を置き換えるために指定されたポインター。

#### <a name="example"></a>例

```cpp
// auto_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

## <a name="see-also"></a>関連項目

[unique_ptr クラス](../standard-library/unique-ptr-class.md)
