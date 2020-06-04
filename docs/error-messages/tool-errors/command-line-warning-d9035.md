---
title: コマンド ラインの警告 D9035
ms.date: 12/10/2018
f1_keywords:
- D9035
helpviewer_keywords:
- D9035
ms.assetid: 6254f933-e37a-45ba-b860-1a870d1bc8e8
ms.openlocfilehash: 778830892bca1cbf3520599eb6e918e56bdf17ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196639"
---
# <a name="command-line-warning-d9035"></a>コマンド ラインの警告 D9035

> オプション '*option*' は非推奨とされており、今後のリリースで削除される予定です

## <a name="remarks"></a>解説

コンパイラの将来のリリースで削除されるコンパイラオプションを指定しました。 推奨される置換*オプション*がある場合、この警告には警告[D9036](../../error-messages/tool-errors/command-line-warning-d9036.md)が続きます。

指定されたオプションは引き続き機能しますが、ここでビルド構成を更新する必要があります。 その結果、コンパイラをアップグレードすると、プロジェクトのビルドが続行される可能性が高くなります。

## <a name="see-also"></a>参照

[非推奨のコンパイラオプションと削除されたコンパイラオプション](../../build/reference/compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options)<br/>
[コマンド ラインの警告 D9036](command-line-warning-d9036.md)
