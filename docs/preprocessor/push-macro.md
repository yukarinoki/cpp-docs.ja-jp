---
title: push_macro |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.push_macro
- push_macro_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, push_macro
- push_macro pragma
ms.assetid: ac89efc9-afd1-4dfe-bfd1-497229b3e81d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6a389289f8849ac6155543299392586dcd389d2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078948"
---
# <a name="pushmacro"></a>push_macro
値を保存、 *macro_name*このマクロのスタックの上部にあるマクロ。

## <a name="syntax"></a>構文

```
#pragma push_macro("
macro_name
")
```

## <a name="remarks"></a>Remarks

値を取得する*macro_name*で`pop_macro`します。

参照してください[pop_macro](../preprocessor/pop-macro.md)サンプルについては、します。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)