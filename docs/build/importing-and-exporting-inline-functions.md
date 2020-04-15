---
title: インライン関数のインポートとエクスポート
ms.date: 11/04/2016
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
ms.openlocfilehash: abb0443ab8fbd315524350caaff34e0250147ed2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328511"
---
# <a name="importing-and-exporting-inline-functions"></a>インライン関数のインポートとエクスポート

インポートされた関数はインラインとして定義できます。 この効果は、標準関数をインラインで定義する場合とほぼ同じです。関数の呼び出しは、マクロと同様にインライン コードに展開されます。 これは主に、効率のためにメンバー関数の一部をインライン化する可能性のある DLL で C++ クラスをサポートする方法として役立ちます。

インポートされたインライン関数の 1 つの機能は、C++ でそのアドレスを取ることができるということです。 コンパイラは、DLL に存在するインライン関数のコピーのアドレスを返します。 インポートされたインライン関数のもう 1 つの機能は、インポートされたグローバル データとは異なり、インポートされた関数の静的ローカル データを初期化できることです。

> [!CAUTION]
> インポートされたインライン関数を提供する場合は、バージョンの競合の可能性があるため、注意が必要です。 インライン関数はアプリケーション コードに展開されます。したがって、後で関数を書き直しても、アプリケーション自体が再コンパイルされない限り、関数は更新されません。 (通常、DLL 関数は、DLL 関数を使用するアプリケーションを再構築せずに更新できます。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [DLL からのエクスポート](exporting-from-a-dll.md)

- [を使用して DLL からエクスポートします。DEF ファイル](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使った DLL からのエクスポート](exporting-from-a-dll-using-declspec-dllexport.md)

- [AFX_EXT_CLASS を使ったエクスポート/インポート](exporting-and-importing-using-afx-ext-class.md)

- [C 言語の実行形式で使う C++ 関数のエクスポート](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [使用するエクスポート方法を決定する](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

## <a name="see-also"></a>関連項目

[インポートとエクスポート](importing-and-exporting.md)
