---
title: 致命的なエラー C1900
ms.date: 11/04/2016
f1_keywords:
- C1900
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
ms.openlocfilehash: 6a802928315126b72397ba6e8cc61b66f46deb41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202841"
---
# <a name="fatal-error-c1900"></a>致命的なエラー C1900

> '*Tool1*' バージョン '*number1*' と '*tool2*' バージョン '*number2*' が一致しません。

コンパイラのさまざまなパスで実行されたツールが一致しません。 *number1*と*number2*は、ファイルの日付を表します。 たとえば、パス 1 ではコンパイラ フロントエンドが (c1.dll) を実行し、パス 2 ではコンパイラ バックエンドが (c2.dll) を実行します。 ファイルの日付が一致する必要があります。

この問題を解決するには、Visual Studio のすべての更新プログラムが適用されたことを確認します。 問題が引き続き発生する場合は、Windows コントロールパネルの **[プログラムと機能]** を使用して、Visual Studio を修復または再インストールします。
