---
description: 詳細については、「NMAKE の致命的なエラー U1035」を参照してください。
title: NMAKE の致命的なエラー U1035
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: e41b65cbec43a0b19e06767c555df9cfede9b69c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197752"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE の致命的なエラー U1035

構文エラー: 区切り記号 ': ' または ' = ' が必要です

コロン (**:**) または等号 () のいずれか **=** が必要です。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. コロンはターゲットに従っていませんでした。

1. コロンとスペースなし (a:)1文字のターゲットに従います。 NMAKE はドライブ指定として解釈します。

1. コロンは推論規則に従っていませんでした。

1. マクロ定義の後に等号がありませんでした。

1. **\\** 新しい行にコマンドを続行するために使用された円記号 () の後に続く文字。

1. NMAKE の構文規則に従っていない文字列が表示されました。

1. メイクファイルはワードプロセッサによって書式設定されました。
