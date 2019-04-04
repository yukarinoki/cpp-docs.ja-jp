---
title: COM および .NET C++ 属性
ms.custom: index-page
ms.date: 11/19/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI], reference topics
ms.assetid: 613a3611-b3eb-4347-aa38-99b654600e1c
ms.openlocfilehash: f9d339860e9d2bdb8d66f6b7f8f49d3993b2d5cf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820742"
---
# <a name="c-attributes-for-com-and-net"></a>COM および .NET C++ 属性

Microsoft では、COM プログラミングと .NET Framework 共通言語ランタイムの開発を簡略化する C++ 属性のセットを定義します。 ソース ファイルで属性を追加するときに、コンパイラは、プロバイダー コードを挿入または生成されたオブジェクト ファイル内のコードを変更する Dll で機能します。 これらの属性は、.idl ファイル、インターフェイス、タイプ ライブラリ、およびその他の COM 要素の作成を支援します。 統合開発環境 (IDE) で属性は、[プロパティ] ウィンドウと、ウィザードによってサポートします。

属性は、COM オブジェクトを記述するために必要な詳細なコーディングの一部をなくすため中に、バック グラウンド必要があります。 [COM fundamentals](/windows/desktop/com/the-component-object-model)に最大限に活用します。

> [!NOTE]
> C++ の標準的な属性を探している場合は、[属性](../../cpp/attributes.md)を参照してください。

## <a name="purpose-of-attributes"></a>属性の目的

属性は、方向は現在不可能で、言語の従来の構造を損なうことがなく C++ を拡張します。 属性は、プロバイダーの言語機能を動的に拡張する (個別の Dll) を使用します。 属性の主な目的が、コンポーネントの開発者の生産性を高めるだけでなく、COM コンポーネントの作成を簡素化します。 属性を適用するクラス、データ メンバー、またはメンバー関数など、ほぼすべての C++ コンストラクトにします。 この新しいテクノロジが提供する利点の強調表示を次に示します。

- 親しみやすく、単純な呼び出し規則を公開します。

- 使用は、マクロとは異なり、デバッガーによって認識されているコードを挿入します。

- 簡単に大きな負担の実装の詳細なしの基本クラスから派生を使用できます。

- 大量の簡潔ないくつかの属性を持つ COM コンポーネントで必要な IDL コードに置き換えます。

たとえば、ATL のジェネリック クラスの単純なイベント シンクを実装する可能性がありますを適用する、 [event_receiver](event-receiver.md)など特定のクラスに属性`CMyReceiver`します。 `event_receiver`属性は、オブジェクト ファイルに適切なコードを挿入する Visual C コンパイラでコンパイルされます。

```cpp
[event_receiver(com)]
class CMyReceiver
{
   void handler1(int i) { ... }
   void handler2(int i, float j) { ... }
}
```

設定することができますし、`CMyReceiver`メソッド`handler1`と`handler2`イベントを処理する (組み込み関数を使用して[_ _hook](../../cpp/hook.md)) を使用して作成できるイベント ソースから[event_source](event-source.md).

## <a name="basic-mechanics-of-attributes"></a>属性の基本的なしくみ

プロジェクトに属性を挿入する次の 3 つの方法はあります。 最初に挿入できますに手動でソース コード。 次に、プロジェクトでオブジェクトのプロパティ グリッドを使用してそれらを挿入できます。 最後に、さまざまなウィザードを使用してそれらを挿入できます。 使用しての詳細については、**プロパティ**ウィンドウとさまざまなウィザードを参照してください。 [Visual c プロジェクトの管理の作成と](../../build/creating-and-managing-visual-cpp-projects.md)します。

としてする前に、プロジェクトをビルドするとき、コンパイラ解析各 C++ ソース ファイルのオブジェクト ファイルを生成します。 ただし、コンパイラが属性を検出する場合は解析し、構文を検査します。 コンパイラに動的を呼び出してコードを挿入またはコンパイル時にその他の変更、属性プロバイダー。 プロバイダーの実装は、属性の型によって異なります。 たとえば、ATL 関連の属性は、Atlprov.dll によって実装されます。

次の図は、コンパイラと属性プロバイダー間のリレーションシップを示しています。

![コンポーネント属性コミュニケーション](../media/vccompattrcomm.gif "コンポーネント属性コミュニケーション")

> [!NOTE]
> 属性の使用方法には、ソース ファイルの内容は変更されません。 属性が生成されたコードが表示される唯一の時間は、デバッグ セッション中には。 さらに、プロジェクト内の各ソース ファイルの属性を置換した結果を表示するテキスト ファイルを生成できます。 この手順の詳細については、[/Fx (挿入されたコードのマージ)](../../build/reference/fx-merge-injected-code.md)と[挿入されたコードのデバッグ](/visualstudio/debugger/how-to-debug-injected-code)を参照してください。

ほとんどの C++ 構造体のような属性は、適切な使用方法を定義する一連の特性があります。 これは、操作を行うと、属性のコンテキストと呼ばは、属性コンテキストの表の各属性のリファレンス トピックで対処されます。 たとえば、[コクラス](coclass.md)属性のみ適用できますを既存のクラスまたは構造体ではなく、 [cpp_quote](cpp-quote.md)属性には、C++ ソース ファイル内のどこにでも挿入できます。

## <a name="building-an-attributed-program"></a>属性付きプログラムの作成

Visual C 属性をソース コードに追加した後のタイプ ライブラリおよび .idl ファイルを生成するために、Visual C コンパイラをする可能性があります。 次のリンカー オプションの .tlb および .idl ファイルの構築に役立つ。

- [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)

- [/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)

- [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)

いくつかのプロジェクトには、複数の独立した .idl ファイルが含まれます。 これらは、2 つ以上の .tlb ファイルを生成し、必要に応じてリソース ブロックにバインドに使用されます。 このシナリオは、Visual C では現在サポートされていません。

さらに、Visual C リンカーは、1 つの MIDL ファイルにすべての属性の IDL に関連する情報を出力します。 1 つのプロジェクトから 2 つのタイプ ライブラリを生成する方法されません。

## <a name="contexts"></a> 属性コンテキスト

C++ 属性は、次の 4 つの基本的なフィールドを使用して記述できます: に適用できますターゲット (**適用先**) 場合は、反復可能かどうか (**Repeatable**)、その他の属性 (の存在を必要な**必要な属性**)、およびその他の属性の非互換性 (**無効な属性**)。 これらのフィールドは、各属性の参照トピックの表に表示されます。 これらの各フィールドについて、次に示します。

### <a name="applies-to"></a>対象

このフィールドには、指定した属性の有効な対象となっているさまざまな C++ 言語要素について説明します。 たとえば、属性で"class"を指定する場合、**適用先**フィールド、属性は、有効な C++ クラスにのみ適用できますこれを示します。 属性はクラスのメンバー関数に適用する場合、構文エラーが発生します。

詳細については、[属性を使用して](attributes-by-usage.md)を参照してください。

### <a name="repeatable"></a>反復可能

このフィールドは、同じターゲットに属性を繰り返し適用するかどうかを示します。 属性の大半は、反復可能はありません。

### <a name="required-attributes"></a>必要な属性

このフィールドに表示されるその他の属性が必要な適切に機能する指定した属性のある (つまり、同じターゲットに適用される)。 このフィールドのすべてのエントリが存在する属性の一般的なことはできません。

### <a name="invalid-attributes"></a>無効な属性

このフィールドは、指定した属性と互換性があるその他の属性を一覧表示します。 このフィールドのすべてのエントリが存在する属性の一般的なことはできません。

## <a name="in-this-section"></a>このセクションの内容

[属性プログラミングの FAQ](attribute-programming-faq.md)<br/>
[グループ別の属性](attributes-by-group.md)<br/>
[使用法別の属性](attributes-by-usage.md)<br/>
[属性リファレンス (アルファベット順)](attributes-alphabetical-reference.md)