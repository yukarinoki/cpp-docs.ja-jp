---
title: アプリケーションへのインポート
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], importing
- importing DLLs [C++], applications
- applications [C++], importing into
ms.assetid: 9d646466-e12e-4710-8ad9-c819c0375fcc
ms.openlocfilehash: 7b858b2ed1b07c143ba24bacbc51c6bba50e3860
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231521"
---
# <a name="importing-into-an-application"></a>アプリケーションへのインポート

次の 2 つの方法を使用して関数をアプリケーションにインポートできます。

- メイン アプリケーションの関数定義でキーワード **`__declspec(dllimport)`** を使用する

- **`__declspec(dllimport)`** と共にモジュール定義 (.def) ファイルを使用する

## <a name="what-do-you-want-to-do"></a>実行する操作

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [__declspec(dllimport) を使用して関数呼び出しをインポートする](importing-function-calls-using-declspec-dllimport.md)

- [__declspec(dllimport) を使用してデータをインポートする](importing-data-using-declspec-dllimport.md)

- [DEF ファイルを使用してインポートする](importing-using-def-files.md)

## <a name="see-also"></a>関連項目

[インポートとエクスポート](importing-and-exporting.md)
