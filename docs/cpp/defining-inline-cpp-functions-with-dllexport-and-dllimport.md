---
title: dllexport と dllimport を使用したインライン C++ 関数の定義
ms.date: 11/04/2016
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
ms.openlocfilehash: cf3c73e21834391d894a2924f78f6e6143c3a2b6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221719"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport と dllimport を使用したインライン C++ 関数の定義

**Microsoft 固有の仕様**

属性を使用して、関数をインラインで定義でき **`dllexport`** ます。 この場合、関数は、プログラムのモジュールがその関数を参照しているかどうかにかかわらず、常にインスタンス化され、エクスポートされます。 関数は、他のプログラムによってインポートされることを前提としています。

属性を使用して宣言された関数をインラインとして定義することもでき **`dllimport`** ます。 この場合、関数は、(/Ob の指定に応じて) 展開はできても、インスタンス化はできません。 特に、インラインでインポートされた関数のアドレスが使用される場合、DLL 内の関数のアドレスが返されます。 この動作は、インポートされた非インライン関数のアドレスを受け取ることと同じです。

これらの規則は、クラス定義内に定義が出現するインライン関数に適用されます。 また、インライン関数の静的なローカル データと文字列は、単一のプログラム (つまり、DLL インターフェイスのない実行可能ファイル) 内に存在している場合のように、同じ ID を DLL とクライアント間で保持します。

インポートされたインライン関数を用意する場合は注意が必要です。 たとえば、DLL を更新する場合は、クライアントが変更されたバージョンの DLL を使用すると仮定しないでください。 適切なバージョンの DLL が読み込まれるように、DLL のクライアントもリビルドしてください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[dllexport、dllimport](../cpp/dllexport-dllimport.md)
