---
title: 致命的なエラー C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: af43ddb83e872762f720b156644e0d466957a8a7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203880"
---
# <a name="fatal-error-c1092"></a>致命的なエラー C1092

エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。

前回成功したビルド以降にデータ型が変更または追加されました。

- エディットコンティニュは、クラス、構造体、または列挙型の定義など、既存のデータ型への変更をサポートしていません。 デバッグを停止し、アプリケーションをビルドする必要があります。

- エディットコンティニュでは、vc*x*0 .pdb ( *x*は使用中のビジュアルC++のメジャーバージョン) などのプログラムデータベースファイルが読み取り専用の場合、新しいデータ型の追加はサポートされません。 データ型を追加するには、コンパイラが書き込みモードで .pdb ファイルを開く必要があります。

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>現在のデバッグセッションを終了せずにこのエラーを削除するには

1. データ型をエラーが起こる前の状態に戻します。

1. **[デバッグ]** メニューの **[コード変更を適用]** をクリックします。

### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには

1. **[デバッグ]** メニューの **[デバッグの停止]** をクリックします。

1. **[ビルド]** メニューの **[ビルド]** をクリックします。

詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。
