---
title: Comptr::operator-&gt;演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 417fd11017f9f70ee8cc247898e23741488ae5e7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599989"
---
# <a name="comptroperator-gt-operator"></a>Comptr::operator-&gt;演算子

現在のテンプレート パラメーターで指定された型へのポインターを取得します。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;
```

## <a name="return-value"></a>戻り値

現在のテンプレート型名で指定された型へのポインター。

## <a name="remarks"></a>Remarks

このヘルパー関数は、STDMETHOD マクロを使用することで、不要なオーバーヘッドを削除します。 この関数は、`IUnknown`型**プライベート**の代わりに**仮想**します。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[ComPtr クラス](../windows/comptr-class.md)