---
title: 'operator&lt; 演算子 (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 04f5598667f7e0e036f0a55cd3f9cc52b5356299
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213643"
---
# <a name="operatorlt-operator-microsoftwrl"></a>operator&lt; 演算子 (Microsoft:: WRL)

あるオブジェクトのアドレスがもう一方のオブジェクトより小さいかどうかを判断します。

## <a name="syntax"></a>構文

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>パラメーター

*a*<br/>
左側のオブジェクト。

*b*<br/>
右側のオブジェクト。

## <a name="return-value"></a>戻り値

のアドレスが*b*のアドレスより小さい*場合は* **true** 。それ以外の場合は**false**。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
