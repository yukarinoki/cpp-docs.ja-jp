---
description: 詳細については、Command-Line Warning D9035 を参照してください。
title: コマンド ラインの警告 D9035
ms.date: 12/10/2018
f1_keywords:
- D9035
helpviewer_keywords:
- D9035
ms.assetid: 6254f933-e37a-45ba-b860-1a870d1bc8e8
ms.openlocfilehash: a5e667406a16c6da89f5552844ee87899aa14ba0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136098"
---
# <a name="command-line-warning-d9035"></a>コマンド ラインの警告 D9035

> オプション '*option*' は非推奨とされており、今後のリリースで削除される予定です

## <a name="remarks"></a>解説

コンパイラの将来のリリースで削除されるコンパイラオプションを指定しました。 推奨される置換 *オプション* がある場合、この警告には警告 [D9036](../../error-messages/tool-errors/command-line-warning-d9036.md)が続きます。

指定されたオプションは引き続き機能しますが、ここでビルド構成を更新する必要があります。 その結果、コンパイラをアップグレードすると、プロジェクトのビルドが続行される可能性が高くなります。

## <a name="see-also"></a>関連項目

[非推奨のコンパイラオプションと削除されたコンパイラオプション](../../build/reference/compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options)<br/>
[コマンドラインの警告 D9036](command-line-warning-d9036.md)
