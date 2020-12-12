---
description: '詳細情報: WeakReference クラス'
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
ms.openlocfilehash: 743a705fae93d015d190df24d2534de62613e542
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116550"
---
# <a name="weakreference-class"></a>WeakReference クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
class WeakReference;
```

## <a name="remarks"></a>解説

Windows ランタイムまたは従来の COM と共に使用できる *弱い参照* を表します。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。

オブジェクトは、オブジェクトへのポインターである強い参照 `WeakReference` と、メソッドによって配布された強い参照のコピーの数である強い参照 *カウント* を保持します `Resolve()` 。 強い参照カウントが0以外の場合、強い参照は有効で、オブジェクトにアクセスできます。 強い参照カウントがゼロになると、強い参照は無効になり、オブジェクトにアクセスできなくなります。

オブジェクトは、 `WeakReference` 通常、外部のスレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すために使用されます。 たとえば、 `WeakReference` ファイルオブジェクトへの参照からオブジェクトを構築します。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。

`WeakReference`メソッドはスレッドセーフです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                  | 説明
----------------------------------------------------- | ---------------------------------------------------------------------------
[WeakReference:: WeakReference](#weakreference)        | `WeakReference` クラスの新しいインスタンスを初期化します。
[WeakReference:: ~ WeakReference](#tilde-weakreference) | クラスの現在のインスタンスを破棄 (破棄) `WeakReference` します。

### <a name="public-methods"></a>パブリック メソッド

名前                                                                 | 説明
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference::D ecrementStrongReference](#decrementstrongreference) | 現在のオブジェクトの強い参照カウントをデクリメントし `WeakReference` ます。
[WeakReference:: IncrementStrongReference](#incrementstrongreference) | 現在のオブジェクトの強い参照カウントをインクリメントし `WeakReference` ます。
[WeakReference:: Resolve](#resolve)                                   | 強い参照カウントが0以外の場合に、指定されたポインターを現在の厳密な参照値に設定します。
[WeakReference:: SetUnknown](#setunknown)                             | `WeakReference`指定したインターフェイスポインターに現在のオブジェクトの強い参照を設定します。

## <a name="inheritance-hierarchy"></a>継承階層

`WeakReference`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="weakreferenceweakreference"></a><a name="tilde-weakreference"></a> WeakReference:: ~ WeakReference

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

クラスの現在のインスタンスを初期化解除 `WeakReference` します。

## <a name="weakreferencedecrementstrongreference"></a><a name="decrementstrongreference"></a> WeakReference::D ecrementStrongReference

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>解説

現在のオブジェクトの強い参照カウントをデクリメントし `WeakReference` ます。

強い参照カウントがゼロになると、強い参照はに設定され **`nullptr`** ます。

### <a name="return-value"></a>戻り値

デクリメントされた厳密な参照カウント。

## <a name="weakreferenceincrementstrongreference"></a><a name="incrementstrongreference"></a> WeakReference:: IncrementStrongReference

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>戻り値

インクリメントされた厳密な参照カウント。

### <a name="remarks"></a>解説

現在のオブジェクトの強い参照カウントをインクリメントし `WeakReference` ます。

## <a name="weakreferenceresolve"></a><a name="resolve"></a> WeakReference:: Resolve

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
STDMETHOD(Resolve)
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
インターフェイス ID。

*ppvObject*<br/>
この操作が完了すると、厳密な参照カウントが0以外の場合は、現在の強い参照のコピー。

### <a name="return-value"></a>戻り値

- この操作が成功し、厳密な参照カウントが0の場合に S_OK します。 *PpvObject* パラメーターはに設定されて **`nullptr`** います。

- この操作が成功し、厳密な参照カウントが0以外の場合に S_OK します。 *PpvObject* パラメーターには、強い参照が設定されています。

- それ以外の場合は、この操作が失敗した理由を示す HRESULT。

### <a name="remarks"></a>解説

強い参照カウントが0以外の場合に、指定されたポインターを現在の厳密な参照値に設定します。

## <a name="weakreferencesetunknown"></a><a name="setunknown"></a> WeakReference:: SetUnknown

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>パラメーター

*unk*<br/>
`IUnknown`オブジェクトのインターフェイスへのポインター。

### <a name="remarks"></a>解説

`WeakReference`指定したインターフェイスポインターに現在のオブジェクトの強い参照を設定します。

## <a name="weakreferenceweakreference"></a><a name="weakreference"></a> WeakReference:: WeakReference

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
WeakReference();
```

### <a name="remarks"></a>解説

`WeakReference` クラスの新しいインスタンスを初期化します。

オブジェクトの強い参照ポインター `WeakReference` がに初期化され、 **`nullptr`** 厳密な参照カウントが1に初期化されます。
