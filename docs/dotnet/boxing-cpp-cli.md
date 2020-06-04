---
title: ボックス化 (C++/CLI)
ms.date: 11/04/2016
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
ms.openlocfilehash: df0e220c4f744e78aa5bedce4f956b726f524ff4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208835"
---
# <a name="boxing-ccli"></a>ボックス化 (C++/CLI)

ボックス化とは、値型を `object` 型、または値型によって実装されている任意のインターフェイス型に変換するプロセスです。 共通言語ランタイム (CLR) が値型をボックスに入力すると、値が `System.Object` にラップされ、マネージヒープに格納されます。 ボックス化解除すると、値型がオブジェクトから抽出されます。 ボックス化は暗黙的に行われ、ボックス化解除すると明示的になります。

## <a name="related-articles"></a>関連記事

|タイトル|説明|
|-----------|-----------------|
|[方法: 明示的にボックス化を要求する](../dotnet/how-to-explicitly-request-boxing.md)|変数に対して明示的にボックス化を要求する方法について説明します。|
|[方法: gcnew を使用して値型を作成し、暗黙的なボックス化を使用する](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|`gcnew` を使用して、ガベージコレクトされたマネージヒープに配置できるボックス化された値型を作成する方法を示します。|
|[方法: ボックス化を解除する](../dotnet/how-to-unbox.md)|値をボックス解除および変更する方法について説明します。|
|[標準変換と暗黙のボックス化](../dotnet/standard-conversions-and-implicit-boxing.md)|ボックス化が必要な変換に対して、コンパイラによって標準変換が選択されていることを示します。|
|[C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|ビジュアルC++ドキュメントでの .net プログラミングの最上位レベルの記事です。|
