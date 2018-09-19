---
title: 仮想 (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs:
- C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2471dac12db574aa045142a654effafadbabd732
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092273"
---
# <a name="virtual-c"></a>virtual (C++)

**仮想**キーワードは、仮想関数または仮想基底クラスを宣言します。

## <a name="syntax"></a>構文

```
virtual [type-specifiers] member-function-declarator
virtual [access-specifier] base-class-name
```

#### <a name="parameters"></a>パラメーター

*型指定子*<br/>
仮想メンバー関数の戻り値の型を指定します。

*メンバー関数宣言子*<br/>
メンバー関数を宣言します。

*アクセス指定子*<br/>
基底クラスへのアクセスのレベルを定義**パブリック**、**保護**または**プライベート**します。 前に、または後に表示されることができます、**仮想**キーワード。

*基本クラス名*<br/>
以前に宣言されたクラス型を識別します。

## <a name="remarks"></a>Remarks

参照してください[仮想関数](../cpp/virtual-functions.md)詳細についてはします。

また、次のキーワードを参照してください:[クラス](../cpp/class-cpp.md)、[プライベート](../cpp/private-cpp.md)、[パブリック](../cpp/public-cpp.md)と[保護](../cpp/protected-cpp.md)します。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)