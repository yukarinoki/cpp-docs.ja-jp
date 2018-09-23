---
title: dllexport と dllimport を使用したインライン C 関数の定義 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82612d7502557c88c4abf5a974d42b3bf62c3403
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038712"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport と dllimport を使用したインライン C 関数の定義

**Microsoft 固有の仕様**

`dllexport` 属性を使用すると、関数をインラインとして定義できます。 この場合、関数は、プログラムのモジュールがその関数を参照しているかどうかにかかわらず、常にインスタンス化され、エクスポートされます。 関数は、他のプログラムによってインポートされることを前提としています。

また、**dllimport** 属性付きで宣言された関数をインラインで定義することもできます。 この場合、関数は、(/Ob (インライン) コンパイラ オプションの指定に応じて) 展開はできても、インスタンス化はできません。 特に、インラインでインポートされた関数のアドレスが使用される場合、DLL 内の関数のアドレスが返されます。 この動作は、インポートされた非インライン関数のアドレスを受け取ることと同じです。

インライン関数の静的なローカル データと文字列は、単一のプログラム (つまり、DLL インターフェイスのない実行可能ファイル) 内に存在している場合のように、同じ ID を DLL とクライアント間で保持します。

インポートされたインライン関数を用意する場合は注意が必要です。 たとえば、DLL を更新する場合は、クライアントが変更されたバージョンの DLL を使用すると仮定しないでください。 適切なバージョンの DLL が読み込まれるように、DLL のクライアントもリビルドしてください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[DLL インポートおよびエクスポート関数](../c-language/dll-import-and-export-functions.md)