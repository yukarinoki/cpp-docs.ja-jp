---
title: _com_error::_com_error |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89377e33e56b0796fc850c050c8e79eac86ee07d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040467"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error

**Microsoft 固有の仕様**

構築、 **_com_error**オブジェクト。

## <a name="syntax"></a>構文

```
_com_error(
   HRESULT hr,
   IErrorInfo* perrinfo = NULL,
   bool fAddRef=false) throw( );

_com_error( const _com_error& that ) throw( );
```

#### <a name="parameters"></a>パラメーター

*hr*<br/>
HRESULT 情報。

*perrinfo*<br/>
`IErrorInfo` オブジェクト。

*fAddRef*<br/>
既定値がコンス トラクターに null 以外の AddRef を呼び出すと、`IErrorInfo`インターフェイス。 これにより、正しい参照が、インターフェイスの所有権に渡される一般的なケースでカウント、 **_com_error**などオブジェクトします。

```cpp
throw _com_error(hr, perrinfo);
```

コード所有権の転送をしないかどうか、 **_com_error**オブジェクト、および`AddRef`をオフセットするために必要な`Release`で、 **_com_error**デストラクターとしてオブジェクトを構築次に示します。

```cpp
_com_error err(hr, perrinfo, true);
```

*それ*<br/>
既存の **_com_error**オブジェクト。

## <a name="remarks"></a>Remarks

最初のコンス トラクターは、HRESULT と省略可能な指定された新しいオブジェクトを作成します。`IErrorInfo`オブジェクト。 2 つ目は、既存のコピーを作成します。 **_com_error**オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_com_error クラス](../cpp/com-error-class.md)