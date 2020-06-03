---
title: ComPtr クラス
ms.date: 06/02/2020
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
- client/Microsoft::WRL::ComPtr::As
- client/Microsoft::WRL::ComPtr::AsIID
- client/Microsoft::WRL::ComPtr::AsWeak
- client/Microsoft::WRL::ComPtr::Attach
- client/Microsoft::WRL::ComPtr::ComPtr
- client/Microsoft::WRL::ComPtr::CopyTo
- client/Microsoft::WRL::ComPtr::Detach
- client/Microsoft::WRL::ComPtr::Get
- client/Microsoft::WRL::ComPtr::GetAddressOf
- client/Microsoft::WRL::ComPtr::InternalAddRef
- client/Microsoft::WRL::ComPtr::InternalRelease
- client/Microsoft::WRL::ComPtr::operator&
- client/Microsoft::WRL::ComPtr::operator->
- client/Microsoft::WRL::ComPtr::operator=
- client/Microsoft::WRL::ComPtr::operator==
- client/Microsoft::WRL::ComPtr::operator!=
- client/Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType
- client/Microsoft::WRL::ComPtr::ptr_
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
- client/Microsoft::WRL::ComPtr::Reset
- client/Microsoft::WRL::ComPtr::Swap
- client/Microsoft::WRL::ComPtr::~ComPtr
helpviewer_keywords:
- Microsoft::WRL::ComPtr class
- Microsoft::WRL::ComPtr::As method
- Microsoft::WRL::ComPtr::AsIID method
- Microsoft::WRL::ComPtr::AsWeak method
- Microsoft::WRL::ComPtr::Attach method
- Microsoft::WRL::ComPtr::ComPtr, constructor
- Microsoft::WRL::ComPtr::CopyTo method
- Microsoft::WRL::ComPtr::Detach method
- Microsoft::WRL::ComPtr::Get method
- Microsoft::WRL::ComPtr::GetAddressOf method
- Microsoft::WRL::ComPtr::InternalAddRef method
- Microsoft::WRL::ComPtr::InternalRelease method
- Microsoft::WRL::ComPtr::operator& operator
- Microsoft::WRL::ComPtr::operator-> operator
- Microsoft::WRL::ComPtr::operator= operator
- Microsoft::WRL::ComPtr::operator== operator
- Microsoft::WRL::ComPtr::operator!= operator
- Microsoft::WRL::ComPtr::operator Microsoft::WRL::Details::BoolType operator
- Microsoft::WRL::ComPtr::ptr_ data member
- Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf method
- Microsoft::WRL::ComPtr::Reset method
- Microsoft::WRL::ComPtr::Swap method
- Microsoft::WRL::ComPtr::~ComPtr, destructor
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
ms.openlocfilehash: 612747fe0acfa29acc3f516f1257e80069d5395c
ms.sourcegitcommit: d695bb727bd2b081af4d50127b0242a9a5bdce61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84332254"
---
# <a name="comptr-class"></a>ComPtr クラス

テンプレート パラメーターで指定されたインターフェイスを表す *スマート ポインター* 型を作成します。 `ComPtr` は、基になるインターフェイス ポインターの参照カウントを維持し、参照カウントがゼロになるとそのインターフェイスを自動的に解放します。

## <a name="syntax"></a>構文

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
が `ComPtr` 表すインターフェイス。

*U*<br/>
現在の `ComPtr` がフレンドであるクラス。 (このパラメーターを使用するテンプレートは保護されています)。

## <a name="remarks"></a>解説

`ComPtr<>`基になるインターフェイスポインターを表す型を宣言します。 を使用し `ComPtr<>` て変数を宣言し、矢印のメンバーアクセス演算子 ( `->` ) を使用してインターフェイスメンバー関数にアクセスします。

スマートポインターの詳細については、MSDN ライブラリの[Com コーディング方法](/windows/win32/LearnWin32/com-coding-practices)に関する記事の「Com スマートポインター」サブセクションを参照してください。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前            | 説明
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T*テンプレートパラメーターによって指定された型のシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                             | 説明
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[ComPtr:: ComPtr](#comptr)        | `ComPtr` クラスの新しいインスタンスを初期化します。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。
[ComPtr:: ~ ComPtr](#tilde-comptr) | のインスタンスを初期化解除 `ComPtr` します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                      | 説明
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[ComPtr:: As](#as)                                         | `ComPtr`指定されたテンプレートパラメーターで識別されるインターフェイスを表すオブジェクトを返します。
[ComPtr:: AsIID](#asiid)                                   | 指定し `ComPtr` たインターフェイス ID によって識別されるインターフェイスを表すオブジェクトを返します。
[ComPtr:: AsWeak](#asweak)                                 | 現在のオブジェクトへの弱い参照を取得します。
[ComPtr:: Attach](#attach)                                 | このを、 `ComPtr` 現在のテンプレート型パラメーターで指定されたインターフェイス型に関連付けます。
[ComPtr:: CopyTo](#copyto)                                 | このに関連付けられている現在のまたは指定されたインターフェイス `ComPtr` を、指定した出力ポインターにコピーします。
[Comptr::D etcomp](#detach)                                 | このと `ComPtr` 、それが表すインターフェイスとの関連付けを解除します。
[ComPtr:: Get](#get)                                       | このに関連付けられているインターフェイスへのポインターを取得 `ComPtr` します。
[ComPtr:: GetAddressOf](#getaddressof)                     | このによって表されるインターフェイスへのポインターを格納している[ptr_](#ptr)データメンバーのアドレスを取得し `ComPtr` ます。
[ComPtr:: ReleaseAndGetAddressOf](#releaseandgetaddressof) | このに関連付けられているインターフェイスを解放し、 `ComPtr` [ptr_](#ptr)データメンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。
[ComPtr::Reset](#reset)                                   | このに関連付けられているインターフェイスを解放 `ComPtr` し、新しい参照カウントを返します。
[ComPtr:: Swap](#swap)                                     | 現在のによって管理されているインターフェイスと、 `ComPtr` 指定したによって管理されるインターフェイスを交換し `ComPtr` ます。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                        | 説明
------------------------------------------- | --------------------------------------------------------------------------------
[ComPtr:: InternalAddRef](#internaladdref)   | このに関連付けられているインターフェイスの参照カウントをインクリメントし `ComPtr` ます。
[ComPtr:: InternalRelease](#internalrelease) | このに関連付けられているインターフェイスに対して COM 解放操作を実行 `ComPtr` します。

### <a name="public-operators"></a>パブリック演算子

名前                                                                                           | 説明
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[ComPtr:: operator&](#operator-ampersand)                                                       | 現在ののアドレスを取得し `ComPtr` ます。
[ComPtr:: operator->](#operator-arrow)                                                          | 現在のテンプレート パラメーターで指定された型へのポインターを取得します。
[ComPtr:: operator =](#operator-assign)                                                          | 現在のに値を割り当て `ComPtr` ます。
[ComPtr:: operator = =](#operator-equality)                                                       | 2 つの `ComPtr` オブジェクトが等しいかどうかを示します。
[ComPtr:: operator! =](#operator-inequality)                                                     | 2つのオブジェクトが等しくないかどうかを示し `ComPtr` ます。
[ComPtr:: operator Microsoft:: WRL::D etails:: ブール型](#operator-microsoft-wrl-details-booltype) | `ComPtr`がインターフェイスのオブジェクトの有効期間を管理しているかどうかを示します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                 | 説明
-------------------- | ------------------------------------------------------------------------------------------
[ComPtr::p tr_](#ptr) | このに関連付けられ、このによって管理されるインターフェイスへのポインターを格納し `ComPtr` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="comptrcomptr"></a><a name="tilde-comptr"></a>ComPtr:: ~ ComPtr

のインスタンスを初期化解除 `ComPtr` します。

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="comptras"></a><a name="as"></a>ComPtr:: As

`ComPtr`指定されたテンプレートパラメーターで識別されるインターフェイスを表すオブジェクトを返します。

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* p
) const;

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> p
) const;
```

### <a name="parameters"></a>パラメーター

*U*<br/>
パラメーター *p*で表されるインターフェイス。

*irtran-p*<br/>
`ComPtr`パラメーター *U*によって指定されたインターフェイスを表すオブジェクト。パラメーター *p*で現在のオブジェクトを参照することはできません `ComPtr` 。

### <a name="remarks"></a>解説

最初のテンプレートは、コードで使用する必要があるフォームです。 2つ目のテンプレートは、内部ヘルパーの特殊化です。 [Auto](../../cpp/auto-cpp.md)型推論キーワードなどの C++ 言語機能をサポートしています。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="comptrasiid"></a><a name="asiid"></a>ComPtr:: AsIID

指定し `ComPtr` たインターフェイス ID によって識別されるインターフェイスを表すオブジェクトを返します。

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*irtran-p*<br/>
オブジェクトに ID が*riid*であるインターフェイスがある場合は、 *riid*パラメーターによって指定されたインターフェイスへの二重間接ポインターです。 それ以外の場合は、へのポインター `IUnknown` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="comptrasweak"></a><a name="asweak"></a>ComPtr:: AsWeak

現在のオブジェクトへの弱い参照を取得します。

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>パラメーター

*pWeakRef*<br/>
この操作が完了したときに、弱い参照オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="comptrattach"></a><a name="attach"></a>ComPtr:: Attach

このを、 `ComPtr` 現在のテンプレート型パラメーターで指定されたインターフェイス型に関連付けます。

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
インターフェイス型。

## <a name="comptrcomptr"></a><a name="comptr"></a>ComPtr:: ComPtr

`ComPtr` クラスの新しいインスタンスを初期化します。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。

```cpp
WRL_NOTHROW ComPtr();

WRL_NOTHROW ComPtr(
   decltype(__nullptr)
);

template<class U>
WRL_NOTHROW ComPtr(
   _In_opt_ U *other
);

WRL_NOTHROW ComPtr(
   const ComPtr& other
);

template<class U>
WRL_NOTHROW ComPtr(
   const ComPtr<U> &other,
   typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);

WRL_NOTHROW ComPtr(
   _Inout_ ComPtr &&other
);

template<class U>
WRL_NOTHROW ComPtr(
   _Inout_ ComPtr<U>&& other, typename ENABLE_IF<__is_convertible_to(U*, T*), void *>
);
```

### <a name="parameters"></a>パラメーター

*U*<br/>
*もう一方*のパラメーターの型。

*他の*<br/>
*U*型のオブジェクト。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

最初のコンストラクターは既定のコンストラクターであり、暗黙的に空のオブジェクトを作成します。 2番目のコンストラクターは、空のオブジェクトを明示的に作成する[__nullptr](../../extensions/nullptr-cpp-component-extensions.md)を指定します。

3番目のコンストラクターは、ポインターによって指定されたオブジェクトからオブジェクトを作成します。 ComPtr は、ポイントされたメモリを所有し、それに対する参照カウントを保持するようになりました。

4番目と5番目のコンストラクターは、コピーコンストラクターです。 5番目のコンストラクターは、現在の型に変換できる場合にオブジェクトをコピーします。

6番目と7番目のコンストラクターは移動コンストラクターです。 7番目のコンストラクターは、現在の型に変換できる場合にオブジェクトを移動します。

## <a name="comptrcopyto"></a><a name="copyto"></a>ComPtr:: CopyTo

このに関連付けられている現在のまたは指定されたインターフェイス `ComPtr` を、指定したポインターにコピーします。

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>パラメーター

*U*<br/>
型の名前。

*ptr*<br/>
この操作が完了したときに、要求されたインターフェイスへのポインター。

*riid*<br/>
インターフェイス ID。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、暗黙的な操作が失敗した理由を示す HRESULT `QueryInterface` 。

### <a name="remarks"></a>解説

最初の関数は、このに関連付けられているインターフェイスへのポインターのコピーを返し `ComPtr` ます。 この関数は常に S_OK を返します。

2番目の関数は、 `QueryInterface` このに関連付けられているインターフェイスに対して、 `ComPtr` *riid*パラメーターによって指定されたインターフェイスに対して操作を実行します。

3番目の関数は、 `QueryInterface` このに関連付けられているインターフェイスに対して、 `ComPtr` *U*パラメーターの基になるインターフェイスに対して操作を実行します。

## <a name="comptrdetach"></a><a name="detach"></a>Comptr::D etcomp

この `ComPtr` オブジェクトと、それが表すインターフェイスとの関連付けを解除します。

```cpp
T* Detach();
```

### <a name="return-value"></a>戻り値

このオブジェクトによって表されるインターフェイスへのポインター `ComPtr` 。

## <a name="comptrget"></a><a name="get"></a>ComPtr:: Get

このに関連付けられているインターフェイスへのポインターを取得 `ComPtr` します。

```cpp
T* Get() const;
```

### <a name="return-value"></a>戻り値

このに関連付けられているインターフェイスへのポインター `ComPtr` 。

## <a name="comptrgetaddressof"></a><a name="getaddressof"></a>ComPtr:: GetAddressOf

このによって表されるインターフェイスへのポインターを格納している[ptr_](#ptr)データメンバーのアドレスを取得し `ComPtr` ます。

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>戻り値

変数のアドレス。

## <a name="comptrinternaladdref"></a><a name="internaladdref"></a>ComPtr:: InternalAddRef

このに関連付けられているインターフェイスの参照カウントをインクリメントし `ComPtr` ます。

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>解説

このメソッドは保護されています。

## <a name="comptrinternalrelease"></a><a name="internalrelease"></a>ComPtr:: InternalRelease

このに関連付けられているインターフェイスに対して COM 解放操作を実行 `ComPtr` します。

```cpp
unsigned long InternalRelease();
```

### <a name="remarks"></a>解説

このメソッドは保護されています。

## <a name="comptroperatoramp"></a><a name="operator-ampersand"></a>ComPtr:: operator&amp;

このオブジェクトに関連付けられているインターフェイスを解放 `ComPtr` し、オブジェクトのアドレスを取得し `ComPtr` ます。

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>戻り値

現在のへの弱い参照 `ComPtr` 。

### <a name="remarks"></a>解説

このメソッドは、インターフェイスポインターへの参照を解放するという点で、 [Comptr:: GetAddressOf](#getaddressof)とは異なります。 `ComPtr::GetAddressOf`インターフェイスポインターのアドレスが必要であるものの、そのインターフェイスを解放しない場合は、を使用します。

## <a name="comptroperator-gt"></a><a name="operator-arrow"></a>ComPtr:: operator-&gt;

現在のテンプレート パラメーターで指定された型へのポインターを取得します。

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>戻り値

現在のテンプレートの型名によって指定された型へのポインター。

### <a name="remarks"></a>解説

このヘルパー関数は、STDMETHOD マクロを使用することによって生じる不要なオーバーヘッドを除去します。 この関数は、で `IUnknown` `private` はなく型を作成 `virtual` します。

## <a name="comptroperator"></a><a name="operator-assign"></a>ComPtr:: operator =

現在のに値を割り当て `ComPtr` ます。

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>パラメーター

*U*<br/>
クラス。

*他の*<br/>
型または別の型へのポインター、参照、または右辺値参照 `ComPtr` 。

### <a name="return-value"></a>戻り値

現在のへの参照 `ComPtr` 。

### <a name="remarks"></a>解説

この演算子の最初のバージョンでは、現在のに空の値が割り当てられ `ComPtr` ます。

2番目のバージョンでは、割り当てインターフェイスポインターが現在のインターフェイスポインターと同じでない場合、 `ComPtr` 2 番目のインターフェイスポインターが現在のに割り当てられ `ComPtr` ます。

3番目のバージョンでは、割り当てインターフェイスポインターが現在のに割り当てられ `ComPtr` ます。

4番目のバージョンでは、割り当て値のインターフェイスポインターが現在のインターフェイスポインターと同じでない場合、 `ComPtr` 2 番目のインターフェイスポインターが現在のに割り当てられ `ComPtr` ます。

5番目のバージョンは、コピー演算子です。への参照 `ComPtr` が現在のに割り当てられてい `ComPtr` ます。

6番目のバージョンは、移動セマンティクスを使用するコピー演算子です。`ComPtr`任意の型が静的キャストであり、現在のに割り当てられている場合は、への右辺値参照 `ComPtr` 。

7番目のバージョンは、移動セマンティクスを使用するコピー演算子です。`ComPtr` *U*型のへの右辺値参照は、静的キャストであり、現在のに割り当てられてい `ComPtr` ます。

## <a name="comptroperator"></a><a name="operator-equality"></a>ComPtr:: operator = =

2 つの `ComPtr` オブジェクトが等しいかどうかを示します。

```cpp
bool operator==(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator==(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator==(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>パラメーター

*ある*<br/>
`ComPtr` オブジェクトへの参照です。

*b*<br/>
別のオブジェクトへの参照 `ComPtr` 。

### <a name="return-value"></a>戻り値

最初の演算子は、 `true` オブジェクト*a*がオブジェクト*b*と等しい場合はを生成します。それ以外の場合はを返し `false` ます。

2番目と3番目の演算子は、 `true` オブジェクト*a*がと等しい場合はを、 `nullptr` それ以外の場合はを生成します `false` 。

## <a name="comptroperator"></a><a name="operator-inequality"></a>ComPtr:: operator! =

2つのオブジェクトが等しくないかどうかを示し `ComPtr` ます。

```cpp
bool operator!=(
   const ComPtr<T>& a,
   const ComPtr<U>& b
);

bool operator!=(
   const ComPtr<T>& a,
   decltype(__nullptr)
);

bool operator!=(
   decltype(__nullptr),
   const ComPtr<T>& a
);
```

### <a name="parameters"></a>パラメーター

*ある*<br/>
`ComPtr` オブジェクトへの参照です。

*b*<br/>
別のオブジェクトへの参照 `ComPtr` 。

### <a name="return-value"></a>戻り値

最初の演算子は、オブジェクト a がオブジェクト b と等しくない場合はを生成します。 `true` それ以外の場合はを返し*a* *b* `false` ます。

2番目と3番目の演算子は、オブジェクト a がと等しくない場合はを生成します。 `true` *a* `nullptr` それ以外の場合はを返し `false` ます。

## <a name="comptroperator-microsoftwrldetailsbooltype"></a><a name="operator-microsoft-wrl-details-booltype"></a>ComPtr:: operator Microsoft:: WRL::D etails:: ブール型

`ComPtr`がインターフェイスのオブジェクトの有効期間を管理しているかどうかを示します。

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>戻り値

インターフェイスがこのに関連付けられている場合は、 `ComPtr` [bool struct:: Member](boolstruct-structure.md#member)データメンバーのアドレス。それ以外の場合は `nullptr` 。

## <a name="comptrptr_"></a><a name="ptr"></a>ComPtr::p tr_

このに関連付けられ、このによって管理されるインターフェイスへのポインターを格納し `ComPtr` ます。

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>解説

`ptr_`は、保護された内部のデータメンバーです。

## <a name="comptrreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>ComPtr:: ReleaseAndGetAddressOf

このに関連付けられているインターフェイスを解放し、 `ComPtr` [ptr_](#ptr)データメンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>戻り値

このの[ptr_](#ptr)データメンバーのアドレス `ComPtr` 。

## <a name="comptrreset"></a><a name="reset"></a>ComPtr:: Reset

このに関連付けられているインターフェイスを解放 `ComPtr` し、新しい参照カウントを返します。

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>戻り値

基になるインターフェイスに残っている参照の数 (存在する場合)。

## <a name="comptrswap"></a><a name="swap"></a>ComPtr:: Swap

現在のによって管理されているインターフェイスと、 `ComPtr` 指定したによって管理されるインターフェイスを交換し `ComPtr` ます。

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>パラメーター

*r*<br/>
`ComPtr`。
