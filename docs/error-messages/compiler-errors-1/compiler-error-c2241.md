---
title: コンパイラ エラー C2241 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2241
dev_langs:
- C++
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd97551e0feaecce776cc552353716c67822f273
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055898"
---
# <a name="compiler-error-c2241"></a>コンパイラ エラー C2241

'identifier' : メンバー アクセスは制限されています

コードが、プライベート メンバーまたはプロテクト メンバーにアクセスしようとしています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. メンバーのアクセス レベルを変更します。

1. アクセスする関数の `friend` としてメンバーを宣言します。