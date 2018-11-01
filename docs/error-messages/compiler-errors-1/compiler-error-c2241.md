---
title: コンパイラ エラー C2241
ms.date: 11/04/2016
f1_keywords:
- C2241
helpviewer_keywords:
- C2241
ms.assetid: 2f4e2c2c-b95c-4afe-bbe0-4214cd39d140
ms.openlocfilehash: 88f25931d84fe3884ebecbc97b9ddd73390bacc2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618879"
---
# <a name="compiler-error-c2241"></a>コンパイラ エラー C2241

'identifier' : メンバー アクセスは制限されています

コードが、プライベート メンバーまたはプロテクト メンバーにアクセスしようとしています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. メンバーのアクセス レベルを変更します。

1. アクセスする関数の `friend` としてメンバーを宣言します。