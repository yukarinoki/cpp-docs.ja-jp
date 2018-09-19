---
title: _bstr_t::operator ! | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator!
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- operator!, bstr
- operator !, bstr
ms.assetid: 6e60b5a5-2d28-4eec-9e12-790da8f1fdd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a69bd0245035191f95f874bb6a4383c2e148e0a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070848"
---
# <a name="bstrtoperator-"></a>_bstr_t::operator !

**Microsoft 固有の仕様**

場合にチェック カプセル化された`BSTR`は、NULL 文字列です。

## <a name="syntax"></a>構文

```
bool operator!( ) const throw( );
```

## <a name="return-value"></a>戻り値

TRUE を返す場合、[はい]、ない場合は FALSE。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)