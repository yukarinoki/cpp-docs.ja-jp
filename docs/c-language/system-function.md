---
description: '詳細情報: system 関数'
title: system 関数
ms.date: 11/04/2016
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
ms.openlocfilehash: 094fb3be58c1ff82c823ff79c4181a46b7ddf14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114381"
---
# <a name="system-function"></a>system 関数

**ANSI 4.10.4.5** **system** 関数による文字列の実行の内容とモード

**system** 関数は、コマンド ラインからではなく、C プログラムから内部オペレーティング システム コマンド、.EXE、.COM (Windows NT の .CMD)、または .BAT ファイルを実行します。

system 関数は、コマンド インタープリターを探します。これは通常、Windows NT オペレーティング システムでは CMD.EXE、Windows では COMMAND.COM です。 system 関数は、続いてコマンド インタープリターに引数文字列を渡します。

詳細については、「[system、_wsystem](../c-runtime-library/reference/system-wsystem.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)
