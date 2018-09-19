---
title: _com_error::Error |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d56fcf7faaee9d3b0e02964163aa62372a30a78
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109296"
---
# <a name="comerrorerror"></a>_com_error::Error

**Microsoft 固有の仕様**

コンス トラクターに渡された HRESULT を取得します。

## <a name="syntax"></a>構文

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>戻り値

生の HRESULT 項目は、コンス トラクターに渡されます。

## <a name="remarks"></a>Remarks

カプセル化された HRESULT 項目を取得、`_com_error`オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)