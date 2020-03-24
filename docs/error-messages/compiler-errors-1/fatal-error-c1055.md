---
title: 致命的なエラー C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: c349c09b4931c0a303e7619b364ab237394bd4fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204452"
---
# <a name="fatal-error-c1055"></a>致命的なエラー C1055

コンパイラの制限: キーが不足しています。

ソースファイルに含まれているシンボルが多すぎます。 コンパイラは、シンボルテーブルのハッシュキーを使い果たしました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. ソースファイルを小さなファイルに分割します。

1. 不要なヘッダーファイルを削除します。

1. 新しい変数を作成するのではなく、一時的な変数とグローバル変数を再利用します。
