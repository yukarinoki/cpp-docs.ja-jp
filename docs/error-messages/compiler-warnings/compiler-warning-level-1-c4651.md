---
title: コンパイラの警告 (レベル 1) C4651
ms.date: 11/04/2016
f1_keywords:
- C4651
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
ms.openlocfilehash: bc8131665c970c3b86bb1e84e39636ae8f93897b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199543"
---
# <a name="compiler-warning-level-1-c4651"></a>コンパイラの警告 (レベル 1) C4651

プリコンパイル済みヘッダーに対して ' definition ' が指定されましたが、現在のコンパイル用ではありません

定義はプリコンパイル済みヘッダーが生成されたときに指定されましたが、このコンパイルでは指定されませんでした。

定義はプリコンパイル済みヘッダー内で有効になりますが、コードの残りの部分には適用されません。

プリコンパイル済みヘッダーが/DSYMBOL でビルドされた場合、/Yu コンパイルに/DSYMBOL. がない場合、コンパイラはこの警告を生成します。  /DSYMBOL を/Yu コマンドラインに追加すると、この警告が解決されます。
