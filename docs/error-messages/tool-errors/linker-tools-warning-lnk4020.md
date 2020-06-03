---
title: リンカー ツールの警告 LNK4020
ms.date: 05/29/2018
f1_keywords:
- LNK4020
helpviewer_keywords:
- LNK4020
ms.openlocfilehash: e818909cc0b590b0f7727846cfd7b469e8bc0e3f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194227"
---
# <a name="linker-tools-warning-lnk4020"></a>リンカー ツールの警告 LNK4020

> '*filename*' の型レコードは破損しています。一部のシンボルおよび型は、デバッガーからアクセスできない可能性があります

PDB ファイルのファイル*名*の型レコードが破損しています。

この問題は、多くの場合、他のビルドの問題に関連しています。これが最初に報告されたビルドの問題でない限り、最初に他のエラーと警告に対処します。 これが最初に報告された問題である場合は、ビルドディレクトリをクリーンアップし、プロジェクトをリビルドする必要があります。 並列ビルドプロセスを使用する場合は、ビルドをシリアル化するときにエラーが引き続き発生するかどうかを確認してください。
