---
title: Handlet::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf539082ef88abb5fb27f09d92b73403dc2d03a5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611343"
---
# <a name="handletoperator-operator"></a>HandleT::operator= 演算子

指定した値に移動**HandleT**現在オブジェクト**HandleT**オブジェクト。

## <a name="syntax"></a>構文

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>パラメーター

*h*  
ハンドルを右辺値の参照。

## <a name="return-value"></a>戻り値

現在への参照を**HandleT**オブジェクト。

## <a name="remarks"></a>Remarks

この操作を無効化、 **HandleT**パラメーターで指定されたオブジェクト*h*します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[HandleT クラス](../windows/handlet-class.md)