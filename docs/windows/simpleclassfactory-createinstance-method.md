---
title: Simpleclassfactory::createinstance メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a31d364a6464962b8243cfaced03131a20f9324
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance メソッド

指定されたインターフェイスのインスタンスを作成します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

### <a name="parameters"></a>パラメーター

*pUnkOuter*  
必要があります`nullptr`です。 それ以外の場合、戻り値は CLASS_E_NOAGGREGATION します。

SimpleClassFactory には、集計をサポートしていません。 集計がサポートされていて、作成されるオブジェクト、集計の一部であった`pUnkOuter`集計の管理 IUnknown インターフェイスへのポインターになります。

*riid*  
インターフェイスを作成するには、オブジェクトの ID。

*ppvObject*  
この操作の完了時で指定されたオブジェクトのインスタンスへのポインター、`riid`パラメーター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>コメント

場合&#95; &#95;WRL_STRICT&#95; &#95;が定義されている、assert エラーが発生、クラス テンプレート パラメーターに指定された基本クラスから派生していない場合[RuntimeClass](../windows/runtimeclass-class.md)、または、ClassicCom で構成されていないまたはWinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[SimpleClassFactory クラス](../windows/simpleclassfactory-class.md)