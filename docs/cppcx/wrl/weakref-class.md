---
description: '詳細情報: WeakRef クラス'
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
ms.openlocfilehash: 9c1c3edf7589dfd08e0ebab5389d2ca108d8e73c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339411"
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
|[WeakRef::~WeakRef デストラクター](#tilde-weakref)|クラスの現在のインスタンスを初期化解除 `WeakRef` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[WeakRef::As メソッド](#as)|指定された `ComPtr` インターフェイスを表すように、指定されたポインターパラメーターを設定します。|
|[WeakRef::AsIID メソッド](#asiid)|指定された `ComPtr` インターフェイス ID を表すように、指定されたポインターパラメーターを設定します。|
|[WeakRef::CopyTo メソッド](#copyto)|使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[WeakRef::operator& 演算子](#operator-ampersand-operator)|`ComPtrRef`現在のオブジェクトを表すオブジェクトを返し `WeakRef` ます。|

## <a name="remarks"></a>解説

オブジェクトは、 `WeakRef` オブジェクトに関連付けられている *強い参照* を保持し、有効または無効にすることができます。 `As()` `AsIID()` 強い参照を取得するには、メソッドまたはメソッドを呼び出します。 強い参照が有効な場合、関連付けられているオブジェクトにアクセスできます。 強い参照が無効な場合 ( **`nullptr`** )、関連付けられたオブジェクトにはアクセスできません。

オブジェクトは、 `WeakRef` 通常、外部のスレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すために使用されます。 たとえば、 `WeakRef` ファイルオブジェクトへの参照からオブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。

なお、Windows 10 SDK では [As](#as)、 [AsIID](#asiid) 、 [CopyTo](#copyto) の各メソッドの動作が変更されています。 以前は、これらのメソッドのいずれかを呼び出した後、 `WeakRef` 次のコードに示すように、を使用して、 **`nullptr`** 強い参照が正常に取得されたかどうかを確認できました。

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

上記のコードは、Windows 10 SDK (以降) の使用時には機能しません。 代わりに、に渡されたポインターを確認して **`nullptr`** ください。

```cpp
if (strongRef == nullptr)
{
    wprintf(L"Couldn't get strong ref!");
}
```

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtr`

`WeakRef`

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="weakrefweakref-destructor"></a><a name="tilde-weakref"></a> WeakRef:: ~ WeakRef デストラクター

クラスの現在のインスタンスを初期化解除 `WeakRef` します。

```cpp
~WeakRef();
```

## <a name="weakrefas-method"></a><a name="as"></a> WeakRef:: As メソッド

指定された `ComPtr` インターフェイスを表すように、指定されたポインターパラメーターを設定します。

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

*ptr*<br/>
この操作が完了したときに、パラメーター *U* を表すオブジェクト。

### <a name="return-value"></a>戻り値

- この操作が成功した場合は S_OK します。それ以外の場合は、操作が失敗した理由を示す HRESULT と、 *ptr* がに設定され **`nullptr`** ます。

- この操作が成功したが、現在の `WeakRef` オブジェクトが既に解放されている場合は S_OK します。 パラメーター *ptr* はに設定されて **`nullptr`** います。

- この操作が成功したが、現在の `WeakRef` オブジェクトがパラメーター *U* から派生していない場合は S_OK。パラメーター *ptr* はに設定されて **`nullptr`** います。

### <a name="remarks"></a>解説

パラメーター *U* がの場合 `IWeakReference` 、またはから派生していない場合は、エラーが生成され `IInspectable` ます。

最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、 [auto](../../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。

Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドはインスタンスをに設定しません `WeakRef` **`nullptr`** 。そのため、を確認するエラーチェックコードは避けてください `WeakRef` **`nullptr`** 。 代わりに、 *ptr* を確認 **`nullptr`** してください。

## <a name="weakrefasiid-method"></a><a name="asiid"></a> WeakRef:: AsIID メソッド

指定された `ComPtr` インターフェイス ID を表すように、指定されたポインターパラメーターを設定します。

```cpp
HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IInspectable>* ptr
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ptr*<br/>
この操作が完了したときに、パラメーター *riid* を表すオブジェクト。

### <a name="return-value"></a>戻り値

- この操作が成功した場合は S_OK します。それ以外の場合は、操作が失敗した理由を示す HRESULT と、 *ptr* がに設定され **`nullptr`** ます。

- この操作が成功したが、現在の `WeakRef` オブジェクトが既に解放されている場合は S_OK します。 パラメーター *ptr* はに設定されて **`nullptr`** います。

- この操作が成功したが、現在の `WeakRef` オブジェクトがパラメーター *riid* から派生していない場合は S_OK。 パラメーター *ptr* はに設定されて **`nullptr`** います。 (詳細については、「解説」を参照してください。)

### <a name="remarks"></a>解説

パラメーター *riid* がから派生していない場合、エラーが生成され `IInspectable` ます。 このエラーは、戻り値よりも優先されます。

最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレート (ここでは示されていないが、ヘッダー ファイルでは宣言されている) は、 [auto](../../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。

Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドはインスタンスをに設定しません `WeakRef` **`nullptr`** 。そのため、を確認するエラーチェックコードは避けてください `WeakRef` **`nullptr`** 。 代わりに、 *ptr* を確認 **`nullptr`** してください。

## <a name="weakrefcopyto-method"></a><a name="copyto"></a> WeakRef:: CopyTo メソッド

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
インターフェイスをポインター `IInspectable` します。 *U* がから派生していない場合、エラーが生成され `IInspectable` ます。

*riid*<br/>
インターフェイス ID。 *Riid* がから派生していない場合、エラーが生成され `IWeakReference` ます。

*ptr*<br/>
またはへの二重間接 `IInspectable` ポインター `IWeakReference` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 詳細については、「 **解説**」を参照してください。

### <a name="remarks"></a>解説

S_OK の戻り値はこの操作が成功したことを示しますが、弱い参照が強い参照に解決されたかどうかは示していません。 S_OK が返された場合は、パラメーター *p* が強い参照であることをテストします。つまり、パラメーター *p* はと等しくありません **`nullptr`** 。

Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドはインスタンスをに設定しません `WeakRef` **`nullptr`** 。そのため、のを確認するエラーチェックコードは避けてください `WeakRef` **`nullptr`** 。 代わりに、 *ptr* を確認 **`nullptr`** してください。

## <a name="weakrefoperatoramp-operator"></a><a name="operator-ampersand-operator"></a> WeakRef:: operator &amp; 演算子

`ComPtrRef`現在のオブジェクトを表すオブジェクトを返し `WeakRef` ます。

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()
```

### <a name="return-value"></a>戻り値

`ComPtrRef`現在のオブジェクトを表すオブジェクト `WeakRef` 。

### <a name="remarks"></a>解説

これは、コードで使用することを意図していない内部ヘルパー演算子です。

## <a name="weakrefweakref-constructor"></a><a name="weakref"></a> WeakRef:: WeakRef コンストラクター

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

*ptr*<br/>
現在のオブジェクトを初期化する既存のオブジェクトへのポインター、参照、または右辺値参照 `WeakRef` 。

### <a name="remarks"></a>解説

最初のコンストラクターは、空のオブジェクトを初期化し `WeakRef` ます。 2番目のコンストラクターは、 `WeakRef` インターフェイスへのポインターからオブジェクトを初期化し `IWeakReference` ます。 3番目のコンストラクターは、オブジェクトへの参照からオブジェクトを初期化し `WeakRef` `ComPtr<IWeakReference>` ます。 4番目と5番目のコンストラクターは、オブジェクトを別のオブジェクトから初期化し `WeakRef` `WeakRef` ます。
