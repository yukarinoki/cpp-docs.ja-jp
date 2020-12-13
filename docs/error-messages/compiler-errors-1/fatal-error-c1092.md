---
description: '詳細情報: 致命的なエラー C1092'
title: 致命的なエラー C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: b2a16991784b901202e5d51c0d256ad48305f55f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145133"
---
# <a name="fatal-error-c1092"></a>致命的なエラー C1092

エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。

前回成功したビルド以降にデータ型が変更または追加されました。

- エディットコンティニュは、クラス、構造体、または列挙型の定義など、既存のデータ型への変更をサポートしていません。 デバッグを停止し、アプリケーションをビルドする必要があります。

- エディットコンティニュでは、vc *x* 0 .pdb ( *x* は使用中 Visual C++ のメジャーバージョン) などのプログラムデータベースファイルが読み取り専用の場合、新しいデータ型の追加はサポートされません。 データ型を追加するには、コンパイラが書き込みモードで .pdb ファイルを開く必要があります。

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>現在のデバッグセッションを終了せずにこのエラーを削除するには

1. データ型をエラーが起こる前の状態に戻します。

1. **[デバッグ]** メニューの **[コード変更を適用]** をクリックします。

### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには

1. **[デバッグ]** メニューの **[デバッグの停止]** をクリックします。

1. **[ビルド]** メニューの **[ビルド]** をクリックします。

詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。
