---
title: WeakReference Class1 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference class
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9b7270a03192a6fcf53f0c2ecfd1af07a216243
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595532"
---
# <a name="weakreference-class1"></a>WeakReference Class1

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
class WeakReference;
```

## <a name="remarks"></a>Remarks

表す、*弱い参照*Windows ランタイムまたはクラシック COM で使用できます。 弱い参照は、アクセスできる場合とできない場合があるオブジェクトを表します。

A **WeakReference**オブジェクトを保持、*強い参照*、オブジェクトへのポインターであると*強力な参照カウント*、これは、強力なのコピーの数参照によって配布されて、`Resolve()`メソッド。 強力な参照カウントが 0 以外の場合、強い参照が有効なと、オブジェクトにアクセスします。 強力な参照カウントがゼロになったら、強い参照が有効でないし、オブジェクトにアクセスできません。

A **WeakReference**オブジェクトは通常、外部スレッドまたはアプリケーションによって存在が制御されるオブジェクトを表すために使用します。 たとえば、構築、 **WeakReference**ファイル オブジェクトへの参照からオブジェクト。 ファイルが開いている間、強い参照は有効です。 しかし、ファイルが閉じられた場合、強い参照は無効になります。

**WeakReference**メソッドはスレッド セーフであります。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[WeakReference::WeakReference コンストラクター](../windows/weakreference-weakreference-constructor.md)|新しいインスタンスを初期化、 **WeakReference**クラス。|
|[WeakReference::~WeakReference デストラクター](../windows/weakreference-tilde-weakreference-destructor.md)|初期化を解除 (破棄) の現在のインスタンス、 **WeakReference**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[WeakReference::DecrementStrongReference メソッド](../windows/weakreference-decrementstrongreference-method.md)|強い参照が現在のカウントをデクリメント**WeakReference**オブジェクト。|
|[WeakReference::IncrementStrongReference メソッド](../windows/weakreference-incrementstrongreference-method.md)|現在の強い参照カウントをインクリメント**WeakReference**オブジェクト。|
|[WeakReference::Resolve メソッド](../windows/weakreference-resolve-method.md)|強力な参照カウントが 0 以外の場合、現在の強い参照値に指定されたポインターを設定します。|
|[WeakReference::SetUnknown メソッド](../windows/weakreference-setunknown-method.md)|現在の強い参照を設定**WeakReference**オブジェクトを指定されたインターフェイス ポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

`WeakReference`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)