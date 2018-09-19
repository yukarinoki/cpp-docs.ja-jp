---
title: NMAKE の致命的なエラー U1064 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1064
dev_langs:
- C++
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4240bf2c553957e73d5ead0bdd03ea129450645b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093000"
---
# <a name="nmake-fatal-error-u1064"></a>NMAKE の致命的なエラー U1064

見つかりません。 メイクファイルと指定されたターゲットがありません。

NMAKE のコマンド ラインはメイクファイルまたはターゲットを指定しなかったし、現在のディレクトリにメイクファイルをという名前のファイルが含まれていません。

NMAKE では、メイクファイルまたはコマンド ライン ターゲット (または両方) が必要です。 Nmake メイクファイルを使用できるようにするには、/F オプションを指定するか、現在のディレクトリにメイクファイルをという名前のファイルを配置します。 NMAKE は、メイクファイルが指定されていない場合は、推論規則を使用して、コマンドラインのターゲットを作成できます。