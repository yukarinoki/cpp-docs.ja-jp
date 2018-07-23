---
title: Comptrrefbase::operator IInspectable * * 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0c23ba7ba476b44b44f48b76119776e2f2cb188e
ms.sourcegitcommit: 04d327940787df1297b72d534f388a035d472af0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2018
ms.locfileid: "39181147"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>Comptrrefbase::operator IInspectable\* \*演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Remarks

現在ではキャスト[ptr _](../windows/comptrrefbase-ptr-data-member.md)データ メンバーをポインターを-、-ポインター - IInspectable インターフェイス。

現在の ComPtrRefBase IInspectable から派生していない場合は、エラーが生成されます。

このキャストは使用可能な場合にのみ **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** が定義されています。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ComPtrRefBase クラス](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)
