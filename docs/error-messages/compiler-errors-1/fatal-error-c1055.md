---
title: 致命的なエラー C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: e6df4870d7af49c369be7e513791955599c48326
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636511"
---
# <a name="fatal-error-c1055"></a>致命的なエラー C1055

コンパイラの制限: キーが足りません

ソース ファイルには、シンボルが多すぎますが含まれています。 コンパイラは、シンボル テーブルのハッシュ キー不足になりました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ソース ファイルをより小さなファイルに分割します。

1. 不要なヘッダー ファイルを削除します。

1. 新規に作成するのではなく、一時的およびグローバル変数を再利用します。