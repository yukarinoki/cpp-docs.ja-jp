---
title: 演算子&lt;演算子 (microsoft::wrl) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
dev_langs:
- C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d24968f4c076605a698e1af02c8e3fa3f556610
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589713"
---
# <a name="operatorlt-operator-microsoftwrl"></a>演算子&lt;演算子 (microsoft::wrl)

1 つのオブジェクトのアドレスが他よりも少ないかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>パラメーター

*a*  
左側のオブジェクト。

*b*  
右側のオブジェクト。

## <a name="return-value"></a>戻り値

**true**場合のアドレス *、* のアドレスより小さい*b*、それ以外の**false**します。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)