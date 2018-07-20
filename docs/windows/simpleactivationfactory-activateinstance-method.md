---
title: Simpleactivationfactory::activateinstance メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5af4bfd22302b7694b9bafbc1452d636b19cb3c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889424"
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance メソッド

指定されたインターフェイスのインスタンスを作成します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>パラメーター

*ppvObject*  
この操作の完了時で指定されたオブジェクトのインスタンスへのポインター、`Base`クラス テンプレート パラメーター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>コメント

場合&#95; &#95;WRL_STRICT&#95; &#95;が定義されている、assert エラーが発生、クラス テンプレート パラメーターに指定された基本クラスから派生していない場合[RuntimeClass](../windows/runtimeclass-class.md)、または、WinRt で構成されていないまたはWinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)