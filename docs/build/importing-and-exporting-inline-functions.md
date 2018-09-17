---
title: インポートして、インライン関数をエクスポートする |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting functions [C++], inline functions
- inline functions [C++], importing
- DLLs [C++], importing
- importing functions [C++]
- DLLs [C++], exporting from
- importing inline functions [C++]
- inline functions [C++], exporting
- functions [C++], importing
- functions [C++], exporting
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 431b7c3becffb4e5b2543984fd66cae0a1507738
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726558"
---
# <a name="importing-and-exporting-inline-functions"></a>インライン関数のインポートとエクスポート

インポートされた関数をインラインとして定義できます。 効果は、標準関数のインライン; の定義と同じでは約関数の呼び出しは、マクロと同様に、インライン コードに展開されます。 これは、機能は、効率を高めるため、メンバーのいくつかの関数がインライン クラスで DLL を C++ をサポートする方法、主に便利です。

インポートされたインライン関数の機能の 1 つは、C++ では、そのアドレスを取得できることです。 コンパイラは DLL 内に存在するインライン関数のコピーのアドレスを返します。 インポートされたインライン関数のもう 1 つの機能は、グローバル インポートされたデータとは異なり、インポートされた関数の静的なローカル データを初期化することができます。

> [!CAUTION]
>  バージョン間の競合の可能性があるために、インライン関数インポートを提供する場合は注意が必要です。 インライン関数は、アプリケーション コードに展開されます。そのため、後で、関数を書き直して場合に、も更新されないアプリケーション自体が再コンパイルしない限り、します。 (通常は、DLL 関数を更新できますそれらを使用するアプリケーションを再構築しないで。)

## <a name="what-do-you-want-to-do"></a>実行する操作

- [DLL からのエクスポートします。](../build/exporting-from-a-dll.md)

- [使用して、DLL からエクスポートします。DEF ファイル](../build/exporting-from-a-dll-using-def-files.md)

- [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](../build/exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)

- [エクスポート方式の使用](../build/determining-which-exporting-method-to-use.md)

- [使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>関連項目

[インポートとエクスポート](../build/importing-and-exporting.md)