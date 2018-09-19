---
title: _bstr_t::GetBSTR |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a62cd1c08409fb5915ebf42fa118c1e6124e29f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071862"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 固有の仕様**

`BSTR` でラップされた `_bstr_t` の先頭を指します。

## <a name="syntax"></a>構文

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` の先頭。

## <a name="remarks"></a>Remarks

**GetBSTR**すべて影響`_bstr_t`オブジェクトをその共有を`BSTR`します。 1 つ以上`_bstr_t`を共有できる、`BSTR`コピー コンス トラクターを使用して、**演算子 =**。

## <a name="example"></a>例

参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)使用例について**GetBSTR**します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)