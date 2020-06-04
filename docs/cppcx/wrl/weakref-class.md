---
title: WeakRef クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef
- client/Microsoft::WRL::WeakRef::~WeakRef
- client/Microsoft::WRL::WeakRef::As
- client/Microsoft::WRL::WeakRef::AsIID
- client/Microsoft::WRL::WeakRef::CopyTo
- client/Microsoft::WRL::WeakRef::operator&
- client/Microsoft::WRL::WeakRef::WeakRef
helpviewer_keywords:
- Microsoft::WRL::WeakRef class
- Microsoft::WRL::WeakRef::~WeakRef, destructor
- Microsoft::WRL::WeakRef::As method
- Microsoft::WRL::WeakRef::AsIID method
- Microsoft::WRL::WeakRef::CopyTo method
- Microsoft::WRL::WeakRef::operator& operator
- Microsoft::WRL::WeakRef::WeakRef, constructor
ms.assetid: 572be703-c641-496c-8af5-ad6164670ba1
ms.openlocfilehash: 681f5a64c3e2902c66facbd4f0ac3a3663a7e79d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374253"
---
# <a name="weakref-class"></a>WeakRef クラス

クラシック COM ではなく、Windows ランタイムでのみ使用できる *弱い参照* を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
class WeakRef : public ComPtr<IWeakReference>;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[WeakRef::WeakRef コンストラクター](#weakref)|`WeakRef` クラスの新しいインスタンスを初期化します。|
|[WeakRef::~WeakRef デストラクター](#tilde-weakref)|クラスの現在のインスタンスを初期化解除`WeakRef`します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[WeakRef::As メソッド](#as)|指定した`ComPtr`インターフェイスを表す指定したポインター パラメーターを設定します。|
|[WeakRef::AsIID メソッド](#asiid)|指定した`ComPtr`インターフェイス ID を表す指定したポインター パラメーターを設定します。|
|[WeakRef::CopyTo メソッド](#copyto)|使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[WeakRef::operator& 演算子](#operator-ampersand-operator)|現在`WeakRef`の`ComPtrRef`オブジェクトを表すオブジェクトを返します。|

## <a name="remarks"></a>解説

オブジェクト`WeakRef`は、オブジェクトに関連付けられた*厳密な参照*を保持しており、有効または無効な場合があります。 メソッドを`As()``AsIID()`呼び出して、厳密な参照を取得します。 強い参照が有効な場合、関連付けられているオブジェクトにアクセスできます。 強い参照が無効な場合 (`nullptr`)、関連付けられているオブジェクトにアクセスできません。

オブジェクト`WeakRef`は通常、外部スレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すために使用されます。 たとえば、ファイル オブジェクト`WeakRef`への参照からオブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。

なお、Windows 10 SDK では [As](#as)、 [AsIID](#asiid) 、 [CopyTo](#copyto) の各メソッドの動作が変更されています。 以前は、これらのメソッドのいずれかを呼び出した後で、 `WeakRef` `nullptr`をチェックして、次のコードのように、厳密な参照が正常に取得されたかどうかを確認できることができました。

```cpp
WeakRef wr;
strongComptrRef.AsWeak(&wr);

// Now suppose that the object strongComPtrRef points to no longer exists
// and the following code tries to get a strong ref from the weak ref:
ComPtr<ISomeInterface> strongRef;
HRESULT hr = wr.As(&strongRef);

// This check won't work with the Windows 10 SDK version of the library.
// Check the input pointer instead.
if(wr == nullptr)
{
    wprintf(L"Couldn’t get strong ref!");
}
```

上記のコードは、Windows 10 SDK (以降) の使用時には機能しません。 代わりに、 に渡されたポインターを`nullptr`確認します。

```cpp
if (strongRef == nullptr)
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtr`

`WeakRef`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a>弱い参照::~弱い参照デストラクタ

クラスの現在のインスタンスを初期化解除`WeakRef`します。

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a>WeakRef::メソッドとして

指定した`ComPtr`インターフェイスを表す指定したポインター パラメーターを設定します。

```cpp
template<typename U>
HRESULT As(
   _Out_ ComPtr<U>* ptr
);

template<typename U>
HRESULT As(
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr
);
```

### <a name="parameters"></a>パラメーター

*U*<br/>
インターフェイス ID。

*Ptr*<br/>
この操作が完了すると、パラメーター U を表すオブジェクトが*返されます*。

### <a name="return-value"></a>戻り値

- この操作が成功した場合はS_OK。それ以外の場合は、操作が失敗した理由を示す HRESULT を`nullptr`返し *、ptr*が に設定されます。

- S_OKこの操作が成功したが、現在`WeakRef`のオブジェクトが既に解放されている場合。 *パラメータ ptr*は`nullptr`に設定されています。

- この操作が成功した場合S_OKが、現在`WeakRef`のオブジェクトがパラメータ*U*から派生していない場合。*パラメータ ptr*は`nullptr`に設定されています。

### <a name="remarks"></a>解説

パラメーター *U*が`IWeakReference`、または から`IInspectable`派生していない場合は、エラーが生成されます。

最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、 [auto](../../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。

Windows 10 SDK 以降では、このメソッドは、`WeakRef`弱い`nullptr`参照を取得できなかった場合にインスタンスを設定しないため、 の`WeakRef`を`nullptr`チェックするコードをエラー チェックしないようにする必要があります。 代わりに、 *ptr*をチェックしてください`nullptr`。

## <a name="weakrefasiid-method"></a><a name="asiid"></a>弱い参照::AsIID メソッド

指定した`ComPtr`インターフェイス ID を表す指定したポインター パラメーターを設定します。

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*Ptr*<br/>
この操作が完了すると、パラメータ riid を表すオブジェクトが*返されます*。

### <a name="return-value"></a>戻り値

- この操作が成功した場合はS_OK。それ以外の場合は、操作が失敗した理由を示す HRESULT を`nullptr`返し *、ptr*が に設定されます。

- S_OKこの操作が成功したが、現在`WeakRef`のオブジェクトが既に解放されている場合。 *パラメータ ptr*は`nullptr`に設定されています。

- この操作が成功しても、現在`WeakRef`のオブジェクトがパラメータ*riid*から派生していない場合S_OK。 *パラメータ ptr*は`nullptr`に設定されています。 (詳細については、「解説」を参照してください。)

### <a name="remarks"></a>解説

パラメータ*riid*が から`IInspectable`派生していない場合は、エラーが発生します。 このエラーは、戻り値よりも優先されます。

最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレート (ここでは示されていないが、ヘッダー ファイルでは宣言されている) は、 [auto](../../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。

Windows 10 SDK 以降では、このメソッドは、`WeakRef`弱い`nullptr`参照を取得できなかった場合にインスタンスを設定しないため、 の`WeakRef`を`nullptr`チェックするコードをエラー チェックしないようにする必要があります。 代わりに、 *ptr*をチェックしてください`nullptr`。

## <a name="weakrefcopyto-method"></a><a name="copyto"></a>ウィークレフ::メソッドへのコピー

使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。

```cpp
HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ IInspectable** ptr
);

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
);

HRESULT CopyTo(
   _Deref_out_ IWeakReference** ptr
);
```

### <a name="parameters"></a>パラメーター

*U*<br/>
インターフェイスを`IInspectable`指します。 *U*が から`IInspectable`派生していない場合は、エラーが発生します。

*riid*<br/>
インターフェイス ID。 *riid*が から`IWeakReference`派生していない場合は、エラーが発生します。

*Ptr*<br/>
または への二重間接ポインター `IInspectable` `IWeakReference`。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 詳細については、「解説」を参照**してください**。

### <a name="remarks"></a>解説

S_OK の戻り値はこの操作が成功したことを示しますが、弱い参照が強い参照に解決されたかどうかは示していません。 S_OKが返された場合は、パラメータ*p*が強い参照であることをテストします。つまり、パラメータ*p*が と等`nullptr`しくない場合です。

Windows 10 SDK 以降では、このメソッドは、`WeakRef`弱い`nullptr`参照を取得できなかった場合にインスタンスを設定しないため、 の`WeakRef`を`nullptr`チェックするコードをエラー チェックしないようにする必要があります。 代わりに、 *ptr*をチェックしてください`nullptr`。

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a>弱い参照::&amp;演算子演算子

現在`WeakRef`の`ComPtrRef`オブジェクトを表すオブジェクトを返します。

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>戻り値

現在`ComPtrRef``WeakRef`のオブジェクトを表すオブジェクト。

### <a name="remarks"></a>解説

これは、コードで使用するためのものではない内部ヘルパー演算子です。

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a>弱い参照::弱い参照のコンス トラクター

`WeakRef` クラスの新しいインスタンスを初期化します。

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>パラメーター

*Ptr*<br/>
現在`WeakRef`のオブジェクトを初期化する既存のオブジェクトへのポインター、参照、または右辺値参照。

### <a name="remarks"></a>解説

最初のコンストラクターは、空`WeakRef`のオブジェクトを初期化します。 2 番目のコンストラクターは`WeakRef`、ポインターからインターフェイスへのオブジェクト`IWeakReference`を初期化します。 3 番目のコンストラクターは`WeakRef`、オブジェクトへの参照からオブジェクト`ComPtr<IWeakReference>`を初期化します。 4 番目と 5 番目の`WeakRef`コンストラクターは、`WeakRef`別のオブジェクトのオブジェクトを初期化します。
