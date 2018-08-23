---
title: Classfactory::queryinterface メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80c369d5ccbcc9f83d0f3ff90769a3df5d7ec177
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603413"
---
# <a name="classfactoryqueryinterface-method"></a>ClassFactory::QueryInterface メソッド

パラメーターで指定されたインターフェイスへのポインターを取得します。

## <a name="syntax"></a>構文

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*  
インターフェイス ID。

*ppvObject*  
ときにこの操作が完了すると、パラメーターで指定されたインターフェイスへのポインター *riid*します。

## <a name="return-value"></a>戻り値

成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。

## <a name="requirements"></a>要件

**ヘッダー:** module.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ClassFactory クラス](../windows/classfactory-class.md)