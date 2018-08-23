---
title: Simpleclassfactory::createinstance メソッド |Microsoft Docs
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
ms.openlocfilehash: d9dfb783a8e002f249d5f6b4cc0a45193669efb3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603114"
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance メソッド

指定したインターフェイスのインスタンスを作成します。

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
必要があります**nullptr**、それ以外の戻り値は CLASS_E_NOAGGREGATION します。

SimpleClassFactory には、集計をサポートしていません。 集計がサポートされており、作成されるオブジェクト、集計の一部であった*pUnkOuter*制御へのポインターになります`IUnknown`集計のインターフェイス。

*riid*  
インターフェイスを作成するには、オブジェクトの ID。

*ppvObject*  
ときにこの操作が完了したらで指定されたオブジェクトのインスタンスへのポインター、 *riid*パラメーター。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。

## <a name="remarks"></a>Remarks

場合`__WRL_STRICT__`が定義されている、アサート エラーが生成クラス テンプレート パラメーターで指定された基本クラスから派生していない場合[RuntimeClass](../windows/runtimeclass-class.md)、ClassicCom または WinRtClassicComMix で構成されていないまたは[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[SimpleClassFactory クラス](../windows/simpleclassfactory-class.md)