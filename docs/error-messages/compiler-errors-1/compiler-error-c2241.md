---
description: 詳細については、「コンパイラエラー C2241」を参照してください。
title: コンパイラ エラー C2241
ms.date: 11/04/2016
f1_keywords:
- C2241
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
ms.openlocfilehash: a3f39ead3489217f9ce4bd65f7b555521335a913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302505"
---
# <a name="compiler-error-c2241"></a>コンパイラ エラー C2241

'identifier' : メンバー アクセスは制限されています

コードが、プライベート メンバーまたはプロテクト メンバーにアクセスしようとしています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. メンバーのアクセス レベルを変更します。

1. アクセスする関数のメンバーを宣言し **`friend`** ます。
