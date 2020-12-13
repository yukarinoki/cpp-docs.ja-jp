---
description: '詳細情報: dllexport および dllimport を使用したインライン C++ 関数の定義'
title: dllexport と dllimport を使用したインライン C++ 関数の定義
ms.date: 11/04/2016
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
ms.openlocfilehash: 158fc5a8fa3805763b1a5abc731abc8905310a27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339476"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport と dllimport を使用したインライン C++ 関数の定義

**Microsoft 固有の仕様**

属性を使用して、関数をインラインで定義でき **`dllexport`** ます。 この場合、関数は、プログラムのモジュールがその関数を参照しているかどうかにかかわらず、常にインスタンス化され、エクスポートされます。 関数は、他のプログラムによってインポートされることを前提としています。

また、 **`dllimport`** 属性付きで宣言された関数をインラインで定義することもできます。 この場合、関数は、(/Ob の指定に応じて) 展開はできても、インスタンス化はできません。 特に、インラインでインポートされた関数のアドレスが使用される場合、DLL 内の関数のアドレスが返されます。 この動作は、インポートされた非インライン関数のアドレスを受け取ることと同じです。

これらの規則は、クラス定義内に定義が出現するインライン関数に適用されます。 また、インライン関数の静的なローカル データと文字列は、単一のプログラム (つまり、DLL インターフェイスのない実行可能ファイル) 内に存在している場合のように、同じ ID を DLL とクライアント間で保持します。

インポートされたインライン関数を用意する場合は注意が必要です。 たとえば、DLL を更新する場合は、クライアントが変更されたバージョンの DLL を使用すると仮定しないでください。 適切なバージョンの DLL が読み込まれるように、DLL のクライアントもリビルドしてください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[dllexport、dllimport](../cpp/dllexport-dllimport.md)
