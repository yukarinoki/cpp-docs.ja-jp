---
title: ComPtr クラス
ms.date: 07/26/2019
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
ms.openlocfilehash: 89c09ede972f5bdd5da1dde810cad31733bdf338
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372641"
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
表す`ComPtr`インターフェイス。

*U*<br/>
現在`ComPtr`のクラスがフレンドであるクラス。 (このパラメーターを使用するテンプレートは保護されています)。

## <a name="remarks"></a>解説

`ComPtr<>`基になるインターフェイス ポインターを表す型を宣言します。 変数`ComPtr<>`を宣言し、矢印メンバアクセス演算子 (`->`) を使用してインターフェイス メンバ関数にアクセスします。

スマート ポインターの詳細については、MSDN ライブラリの「COM[コーディングの方法](/windows/win32/LearnWin32/com-coding-practices)」のトピックの「COM スマート ポインター」のサブセクションを参照してください。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前            | 説明
--------------- | ---------------------------------------------------------------
`InterfaceType` | *T*テンプレート パラメーターで指定された型のシノニム。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                             | 説明
-------------------------------- | --------------------------------------------------------------------------------------------------------------------
[コムプター::コムプター](#comptr)        | `ComPtr` クラスの新しいインスタンスを初期化します。 オーバーロードは、既定、コピー、移動、および変換の各コンストラクターを提供します。
[コンプター::~コムプター](#tilde-comptr) | のインスタンスを初期化解除`ComPtr`します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                      | 説明
--------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[コムプター::As](#as)                                         | 指定した`ComPtr`テンプレート パラメーターによって識別されるインターフェイスを表すオブジェクトを返します。
[コンプター::AsIID](#asiid)                                   | 指定した`ComPtr`インターフェイス ID によって識別されるインターフェイスを表すオブジェクトを返します。
[コンプター::アスマイア](#asweak)                                 | 現在のオブジェクトへの弱い参照を取得します。
[コンプター::アタッチ](#attach)                                 | これを`ComPtr`、現在のテンプレート型パラメーターで指定されたインターフェイスの型に関連付けます。
[コンプター::コピート](#copyto)                                 | 指定した出力ポインターに、この`ComPtr`関連付けに関連付けられている現在のインターフェイスまたは指定されたインターフェイスをコピーします。
[コンプトル::Dエタッハ](#detach)                                 | これを`ComPtr`、それが表すインターフェイスとの関連付けを解除します。
[コンプター::ゲット](#get)                                       | に`ComPtr`関連付けられているインターフェイスへのポインターを取得します。
[を見る](#getaddressof)                     | ptr_`ComPtr`[データ](#ptr)メンバのアドレスを取得します。
[をクリックします。](#releaseandgetaddressof) | これに`ComPtr`関連付けられているインターフェイスを解放し、解放されたインターフェイスへのポインターを含む[ptr_](#ptr)データ メンバーのアドレスを取得します。
[ComPtr::Reset](#reset)                                   | この`ComPtr`に関連付けられているインターフェイスへのポインターのすべての参照を解放します。
[コンプター::スワップ](#swap)                                     | 現在`ComPtr`管理するインターフェイスを、指定した`ComPtr`によって管理されるインターフェイスと交換します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                        | 説明
------------------------------------------- | --------------------------------------------------------------------------------
[コンプター::内部AddRef](#internaladdref)   | この`ComPtr`に関連付けられているインターフェイスの参照カウントをインクリメントします。
[コンプター::内部リリース](#internalrelease) | この`ComPtr`に関連付けられたインターフェイスに対して COM リリース操作を実行します。

### <a name="public-operators"></a>パブリック演算子

名前                                                                                           | 説明
---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------
[コムプター::演算子&](#operator-ampersand)                                                       | 現在`ComPtr`の アドレスを取得します。
[コンプター::オペレーター>](#operator-arrow)                                                          | 現在のテンプレート パラメーターで指定された型へのポインターを取得します。
[コンプター::演算子=](#operator-assign)                                                          | 現在`ComPtr`の に値を代入します。
[コンプター::演算子==](#operator-equality)                                                       | 2 つの `ComPtr` オブジェクトが等しいかどうかを示します。
[コンプター::演算子!](#operator-inequality)                                                     | 2 つの `ComPtr` オブジェクトが等しくないかどうかを示します。
[コムプター::オペレーターマイクロソフト:WRL::Dテール::ブールタイプ](#operator-microsoft-wrl-details-booltype) | インターフェイスのオブジェクトの有効期間`ComPtr`を管理するかどうかを示します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                 | 説明
-------------------- | ------------------------------------------------------------------------------------------
[コンプター::ptr_](#ptr) | に関連付けられており、このによって管理されるインターフェイスへのポインターを`ComPtr`格納します。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="comptrcomptr"></a><a name="tilde-comptr"></a>コンプター::~コムプター

のインスタンスを初期化解除`ComPtr`します。

```cpp
WRL_NOTHROW ~ComPtr();
```

## <a name="comptras"></a><a name="as"></a>コムプター::As

指定した`ComPtr`テンプレート パラメーターによって識別されるインターフェイスを表すオブジェクトを返します。

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
パラメータ*p*で表されるインタフェース。

*P*<br/>
U`ComPtr`パラメータで指定されたインタフェースを表*U*すオブジェクト。パラメーター *p*は、現行`ComPtr`オブジェクトを参照してはなりません。

### <a name="remarks"></a>解説

最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、 [auto](../../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="comptrasiid"></a><a name="asiid"></a>コンプター::AsIID

指定した`ComPtr`インターフェイス ID によって識別されるインターフェイスを表すオブジェクトを返します。

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*P*<br/>
オブジェクトに、ID が*riid*に等しいインターフェイスがある場合は *、riid*パラメータで指定されたインターフェイスへの二重間接ポインタ。それ以外の場合は`IUnknown`、 へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="comptrasweak"></a><a name="asweak"></a>コンプター::アスマイア

現在のオブジェクトへの弱い参照を取得します。

```cpp
HRESULT AsWeak(
   _Out_ WeakRef* pWeakRef
);
```

### <a name="parameters"></a>パラメーター

*を見る*<br/>
この操作が完了すると、弱参照オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="comptrattach"></a><a name="attach"></a>コンプター::アタッチ

これを`ComPtr`、現在のテンプレート型パラメーターで指定されたインターフェイスの型に関連付けます。

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>パラメーター

*他*<br/>
インターフェイス型。

## <a name="comptrcomptr"></a><a name="comptr"></a>コムプター::コムプター

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
*他*のパラメーターの型。

*他*<br/>
*U*型のオブジェクト。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

最初のコンストラクターは既定のコンストラクターで、空のオブジェクトが作成されます。 2 番目のコンストラクターは[、空の](../../extensions/nullptr-cpp-component-extensions.md)オブジェクトを明示的に作成する __nullptr を指定します。

3 番目のコンストラクターは、ポインターで指定されたオブジェクトからオブジェクトを作成します。 ComPtr は、現在、指し込み先メモリを所有し、それに対する参照カウントを維持します。

4 番目と 5 番目のコンストラクターはコピー コンストラクターです。 5 番目のコンストラクターは、現在の型に変換できる場合は、オブジェクトをコピーします。

6 番目と 7 番目のコンストラクターは移動コンストラクターです。 7 番目のコンストラクターは、現在の型に変換可能な場合は、オブジェクトを移動します。

## <a name="comptrcopyto"></a><a name="copyto"></a>コンプター::コピート

指定したポインターに、この`ComPtr`関連付けに関連付けられている現在のインターフェイスまたは指定されたインターフェイスをコピーします。

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

*Ptr*<br/>
この操作が完了すると、要求されたインターフェイスへのポインター。

*riid*<br/>
インターフェイス ID。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、暗黙的`QueryInterface`な操作が失敗した理由を示す HRESULT。

### <a name="remarks"></a>解説

最初の関数は、この`ComPtr`に関連付けられたインターフェイスへのポインタのコピーを返します。 この関数は常にS_OK返します。

2 番目の関数`QueryInterface`は *、riid*パラメーターで`ComPtr`指定されたインターフェイスに対して、これに関連付けられたインターフェイスに対して操作を実行します。

3 番目の関数`QueryInterface`は *、U*パラメーターの基`ComPtr`になるインターフェイスに対して、これに関連付けられたインターフェイスに対して操作を実行します。

## <a name="comptrdetach"></a><a name="detach"></a>コンプトル::Dエタッハ

このオブジェクトと、それが`ComPtr`表すインターフェイスとの関連付けを解除します。

```cpp
T* Detach();
```

### <a name="return-value"></a>戻り値

この`ComPtr`オブジェクトによって表されたインターフェイスへのポインター。

## <a name="comptrget"></a><a name="get"></a>コンプター::ゲット

に`ComPtr`関連付けられているインターフェイスへのポインターを取得します。

```cpp
T* Get() const;
```

### <a name="return-value"></a>戻り値

この`ComPtr`に関連付けられているインターフェイスへのポインター。

## <a name="comptrgetaddressof"></a><a name="getaddressof"></a>を見る

ptr_`ComPtr`[データ](#ptr)メンバのアドレスを取得します。

```cpp
T* const* GetAddressOf() const;
T** GetAddressOf();
```

### <a name="return-value"></a>戻り値

変数のアドレス。

## <a name="comptrinternaladdref"></a><a name="internaladdref"></a>コンプター::内部AddRef

この`ComPtr`に関連付けられているインターフェイスの参照カウントをインクリメントします。

```cpp
void InternalAddRef() const;
```

### <a name="remarks"></a>解説

このメソッドは保護されています。

## <a name="comptrinternalrelease"></a><a name="internalrelease"></a>コンプター::内部リリース

この`ComPtr`に関連付けられたインターフェイスに対して COM リリース操作を実行します。

```cpp
void InternalRelease();
```

### <a name="remarks"></a>解説

このメソッドは保護されています。

## <a name="comptroperatoramp"></a><a name="operator-ampersand"></a>コンプター::オペレーター&amp;

この`ComPtr`オブジェクトに関連付けられているインターフェイスを解放し、オブジェクトのアドレスを`ComPtr`取得します。

```cpp
Details::ComPtrRef<WeakRef> operator&()

const Details::ComPtrRef<const WeakRef> operator&() const
```

### <a name="return-value"></a>戻り値

現在`ComPtr`の .

### <a name="remarks"></a>解説

このメソッドは、このメソッドがインターフェイス ポインターへの参照を解放するという点で[ComPtr::GetAddressOf](#getaddressof)とは異なります。 インターフェイス`ComPtr::GetAddressOf`ポインタのアドレスが必要で、そのインターフェイスを解放したくない場合に使用します。

## <a name="comptroperator-gt"></a><a name="operator-arrow"></a>コンプター::オペレーター-&gt;

現在のテンプレート パラメーターで指定された型へのポインターを取得します。

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

### <a name="return-value"></a>戻り値

現在のテンプレート型名で指定された型へのポインター。

### <a name="remarks"></a>解説

このヘルパー関数は、STDMETHOD マクロを使用して生じる不要なオーバーヘッドを除去します。 この関数は`IUnknown`、`private`の`virtual`代わりに型を作成します。

## <a name="comptroperator"></a><a name="operator-assign"></a>コンプター::演算子=

現在`ComPtr`の に値を代入します。

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

*他*<br/>
型または別`ComPtr`の 型へのポインター、参照、または右辺値の参照。

### <a name="return-value"></a>戻り値

現在`ComPtr`の .

### <a name="remarks"></a>解説

この演算子の最初のバージョンでは、現在`ComPtr`の に空の値を割り当てます。

2 番目のバージョンでは、割り当てインターフェイス ポインターが現在`ComPtr`のインターフェイス ポインターと同じでない場合、2 番目の`ComPtr`インターフェイス ポインターが現在の .

3 番目のバージョンでは、割り当てインターフェイス ポインタが`ComPtr`現在の .

4 番目のバージョンでは、代入する値のインターフェイス ポインターが現在`ComPtr`のインターフェイス ポインターと同じでない場合、2 番目のインターフェイス ポインター`ComPtr`が現在の .

5 番目のバージョンはコピー演算子です。への参照が現在`ComPtr``ComPtr`の に割り当てられます。

6 番目のバージョンは、移動セマンティクスを使用するコピー演算子です。いずれかの型が静的キャストされ`ComPtr`、現在`ComPtr`の .

7 番目のバージョンは、移動セマンティクスを使用するコピー演算子です。`ComPtr` *U*型への右辺値参照は静的キャストされ、現在`ComPtr`の に割り当てられます。

## <a name="comptroperator"></a><a name="operator-equality"></a>コンプター::演算子==

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

*A*<br/>
`ComPtr` オブジェクトへの参照です。

*B*<br/>
別`ComPtr`のオブジェクトへの参照。

### <a name="return-value"></a>戻り値

最初の演算子は`true`、オブジェクト*a*がオブジェクト*b*と等しい場合に生成されます。それ以外`false`の場合は、 .

2 番目と 3`true`番目の演算子は、`nullptr`オブジェクト*a*が 次の値に等しい場合に返します。それ以外`false`の場合は、 .

## <a name="comptroperator"></a><a name="operator-inequality"></a>コンプター::演算子!

2 つの `ComPtr` オブジェクトが等しくないかどうかを示します。

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

*A*<br/>
`ComPtr` オブジェクトへの参照です。

*B*<br/>
別`ComPtr`のオブジェクトへの参照。

### <a name="return-value"></a>戻り値

最初の演算子は`true`、オブジェクト*a*がオブジェクト*b*と等しくない場合に生成されます。それ以外`false`の場合は、 .

2 番目と 3`true`番目の演算子は、オブジェクト`nullptr` *a*が等しくない場合に返します。それ以外`false`の場合は、 .

## <a name="comptroperator-microsoftwrldetailsbooltype"></a><a name="operator-microsoft-wrl-details-booltype"></a>コムプター::オペレーターマイクロソフト:WRL::Dテール::ブールタイプ

インターフェイスのオブジェクトの有効期間`ComPtr`を管理するかどうかを示します。

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

### <a name="return-value"></a>戻り値

インターフェイスがこれに`ComPtr`関連付けられている場合は[、BoolStruct::メンバー](boolstruct-structure.md#member)データ メンバーのアドレス。それ以外`nullptr`の場合は、 .

## <a name="comptrptr_"></a><a name="ptr"></a>コンプター::ptr_

に関連付けられており、このによって管理されるインターフェイスへのポインターを`ComPtr`格納します。

```cpp
InterfaceType *ptr_;
```

### <a name="remarks"></a>解説

`ptr_`は、内部の保護されたデータ メンバーです。

## <a name="comptrreleaseandgetaddressof"></a><a name="releaseandgetaddressof"></a>をクリックします。

これに`ComPtr`関連付けられているインターフェイスを解放し、解放されたインターフェイスへのポインターを含む[ptr_](#ptr)データ メンバーのアドレスを取得します。

```cpp
T** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>戻り値

この`ComPtr`の[ptr_](#ptr)データ メンバのアドレス。

## <a name="comptrreset"></a><a name="reset"></a>コンプター::リセット

この`ComPtr`に関連付けられているインターフェイスへのポインターのすべての参照を解放します。

```cpp
unsigned long Reset();
```

### <a name="return-value"></a>戻り値

解放された参照の数 (存在する場合)。

## <a name="comptrswap"></a><a name="swap"></a>コンプター::スワップ

現在`ComPtr`管理するインターフェイスを、指定した`ComPtr`によって管理されるインターフェイスと交換します。

```cpp
void Swap(
   _Inout_ ComPtr&& r
);

void Swap(
   _Inout_ ComPtr& r
);
```

### <a name="parameters"></a>パラメーター

*R*<br/>
`ComPtr` です。
