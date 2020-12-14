---
description: '詳細情報: 致命的なエラー C1055'
title: 致命的なエラー C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: f85d3bc19b9dcd2ba3f4338e78c55cc7aa549fb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251649"
---
# <a name="fatal-error-c1055"></a>致命的なエラー C1055

コンパイラの制限: キーが不足しています。

ソースファイルに含まれているシンボルが多すぎます。 コンパイラは、シンボルテーブルのハッシュキーを使い果たしました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ソースファイルを小さなファイルに分割します。

1. 不要なヘッダーファイルを削除します。

1. 新しい変数を作成するのではなく、一時的な変数とグローバル変数を再利用します。
