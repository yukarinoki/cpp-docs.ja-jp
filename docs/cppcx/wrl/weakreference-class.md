---
title: WeakReference クラス
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::Resolve
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
- implements/Microsoft::WRL::Details::WeakReference::~WeakReference
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
helpviewer_keywords:
- Microsoft::WRL::Details::WeakReference class
- Microsoft::WRL::Details::WeakReference::DecrementStrongReference method
- Microsoft::WRL::Details::WeakReference::IncrementStrongReference method
- Microsoft::WRL::Details::WeakReference::Resolve method
- Microsoft::WRL::Details::WeakReference::SetUnknown method
- Microsoft::WRL::Details::WeakReference::~WeakReference, destructor
- Microsoft::WRL::Details::WeakReference::WeakReference, constructor
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
ms.openlocfilehash: a80c0ec14da2a955a95ac84dd3975212ef20ae04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374214"
---
# <a name="weakreference-class"></a>WeakReference クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class WeakReference;
```

## <a name="remarks"></a>解説

Windows ランタイムまたはクラシック COM で使用できる*弱い参照*を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。

オブジェクト`WeakReference`は、オブジェクトへのポインタである*強い参照*、 およびメソッドによって配布された厳密参照のコピー数である厳密な*参照カウント*を保持します`Resolve()`。 厳密な参照カウントが 0 以外の場合、厳密な参照は有効であり、オブジェクトはアクセス可能です。 厳密な参照カウントが 0 になると、厳密な参照は無効になり、オブジェクトにアクセスできません。

オブジェクト`WeakReference`は通常、外部スレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すために使用されます。 たとえば、ファイル オブジェクト`WeakReference`への参照からオブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。

メソッド`WeakReference`はスレッド セーフです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                  | 説明
----------------------------------------------------- | ---------------------------------------------------------------------------
[弱い参照::弱い参照](#weakreference)        | `WeakReference` クラスの新しいインスタンスを初期化します。
[弱い参照::~弱い参照](#tilde-weakreference) | `WeakReference`クラスの現在のインスタンスを初期化解除 (破棄) します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                                 | 説明
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[弱い参照::DecrementStrongReference](#decrementstrongreference) | 現在`WeakReference`のオブジェクトの厳密な参照カウントをデクリメントします。
[弱い参照::インクリメントストロングリファレンス](#incrementstrongreference) | 現在`WeakReference`のオブジェクトの厳密な参照カウントをインクリメントします。
[弱い参照::解決](#resolve)                                   | 厳密な参照カウントが 0 以外の場合、指定したポインターを現在の厳密な参照値に設定します。
[弱い参照::設定不明](#setunknown)                             | 現在の`WeakReference`オブジェクトの指定したインターフェイス ポインターへの厳密な参照を設定します。

## <a name="inheritance-hierarchy"></a>継承階層

`WeakReference`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="weakreferenceweakreference"></a><a name="tilde-weakreference"></a>弱い参照::~弱い参照

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

クラスの現在のインスタンスを初期化解除`WeakReference`します。

## <a name="weakreferencedecrementstrongreference"></a><a name="decrementstrongreference"></a>弱い参照::DecrementStrongReference

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>解説

現在`WeakReference`のオブジェクトの厳密な参照カウントをデクリメントします。

厳密な参照カウントが 0 になると、厳密な参照は`nullptr`に設定されます。

### <a name="return-value"></a>戻り値

デクリメントされた強い参照カウント。

## <a name="weakreferenceincrementstrongreference"></a><a name="incrementstrongreference"></a>弱い参照::インクリメントストロングリファレンス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>戻り値

インクリメントされた強い参照カウント。

### <a name="remarks"></a>解説

現在`WeakReference`のオブジェクトの厳密な参照カウントをインクリメントします。

## <a name="weakreferenceresolve"></a><a name="resolve"></a>弱い参照::解決

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*オブジェクト*<br/>
この操作が完了すると、現在の厳密参照のコピー (厳密な参照カウントが 0 以外の場合)。

### <a name="return-value"></a>戻り値

- この操作が成功し、厳密な参照カウントが 0 である場合にS_OKします。 *ppvObject*パラメータは`nullptr`に設定されます。

- この操作が成功し、厳密な参照カウントが 0 以外の場合にS_OKします。 *ppvObject*パラメータは、強い参照に設定されます。

- それ以外の場合は、この操作が失敗した理由を示す HRESULT。

### <a name="remarks"></a>解説

厳密な参照カウントが 0 以外の場合、指定したポインターを現在の厳密な参照値に設定します。

## <a name="weakreferencesetunknown"></a><a name="setunknown"></a>弱い参照::設定不明

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>パラメーター

*アンク*<br/>
オブジェクトの`IUnknown`インターフェイスへのポインター。

### <a name="remarks"></a>解説

現在の`WeakReference`オブジェクトの指定したインターフェイス ポインターへの厳密な参照を設定します。

## <a name="weakreferenceweakreference"></a><a name="weakreference"></a>弱い参照::弱い参照

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
WeakReference();
```

### <a name="remarks"></a>解説

`WeakReference` クラスの新しいインスタンスを初期化します。

オブジェクトの`WeakReference`厳密な参照ポインターが に`nullptr`初期化され、厳密な参照カウントが 1 に初期化されます。
