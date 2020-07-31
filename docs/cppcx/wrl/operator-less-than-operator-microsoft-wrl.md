---
title: 'operator &lt; 演算子 (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: b438f823814e21e2da43f698471d782c88626628
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226881"
---
# <a name="operatorlt-operator-microsoftwrl"></a>operator &lt; 演算子 (Microsoft:: WRL)

あるオブジェクトのアドレスがもう一方のオブジェクトより小さいかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>パラメーター

*ある*<br/>
左側のオブジェクト。

*b*<br/>
右側のオブジェクト。

## <a name="return-value"></a>戻り値

**`true`** のアドレスが*b*のアドレスより小さい*場合は。* それ以外の場合は **`false`** 。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
