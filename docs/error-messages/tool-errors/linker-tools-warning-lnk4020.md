---
description: 詳細については、「リンカーツールの警告 LNK4020」を参照してください。
title: リンカー ツールの警告 LNK4020
ms.date: 05/29/2018
f1_keywords:
- LNK4020
helpviewer_keywords:
- LNK4020
ms.openlocfilehash: 1f658b999f57a8b4eeaa01e2586bc356da5f91a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331962"
---
# <a name="linker-tools-warning-lnk4020"></a>リンカー ツールの警告 LNK4020

> '*filename*' の型レコードは破損しています。一部のシンボルおよび型は、デバッガーからアクセスできない可能性があります

PDB ファイルのファイル *名* の型レコードが破損しています。

この問題は、多くの場合、他のビルドの問題に関連しています。これが最初に報告されたビルドの問題でない限り、最初に他のエラーと警告に対処します。 これが最初に報告された問題である場合は、ビルドディレクトリをクリーンアップし、プロジェクトをリビルドする必要があります。 並列ビルドプロセスを使用する場合は、ビルドをシリアル化するときにエラーが引き続き発生するかどうかを確認してください。
