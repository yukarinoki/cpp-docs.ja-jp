---
title: 致命的なエラー C1092 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9852b7b3d695d5414e52727ce672ee3258f6840b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077153"
---
# <a name="fatal-error-c1092"></a>致命的なエラー C1092

エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。

変更または前回の成功したビルドからデータ型を追加します。

- エディット コンティニュは、クラス、構造体、または列挙型の定義を含む、既存のデータ型に変更をサポートしていません。 デバッグを停止し、アプリケーションをビルドする必要があります。

- エディット コンティニュが vc などのプログラム データベース ファイルの場合、新しいデータ型の追加をサポートしていない*x*0. pdb (場所*x*使用中の Visual C のメジャー バージョン) は読み取り専用です。 データ型を追加するには、コンパイラが、書き込みモードで .pdb ファイルを開く必要があります。

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこのエラーを削除するには

1. データ型をエラーが起こる前の状態に戻します。

1. **[デバッグ]** メニューの **[コード変更を適用]** をクリックします。

### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには

1. **[デバッグ]** メニューの **[デバッグの停止]** をクリックします。

1. **[ビルド]** メニューの **[ビルド]** をクリックします。

詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。