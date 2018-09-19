---
title: C++ 言語リファレンス |Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- language reference
- C++, language reference
- language reference, Visual C++
- Visual C++, language reference
ms.assetid: 4be9cacb-c862-4391-894a-3a118c9c93ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 708db2b20cdbbe2e322075789f64433ff70612a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025517"
---
# <a name="c-language-reference"></a>C++ 言語リファレンス

このリファレンスでは、Microsoft Visual C++ に実装されている C++ プログラミング言語について説明します。 この体系は、Margaret Ellis と Bjarne Stroustrup による*Annotated C++ Reference Manual* および ANSI/ISO C++ 国際規格 (ISO/IEC FDIS 14882) に基づいてます。 Microsoft 固有の C++ 言語機能の実装も含まれます。

最新の C++ プログラミングの概要については、次を参照してください。[C++ へようこそ](welcome-back-to-cpp-modern-cpp.md)に戻ってください。

キーワードまたは演算子をすばやく見つけるには、次の表を参照してください。

- [C++ のキーワード](../cpp/keywords-cpp.md)

- [C++ 演算子](../cpp/cpp-built-in-operators-precedence-and-associativity.md)

## <a name="in-this-section"></a>このセクションの内容

[構文規則](../cpp/lexical-conventions.md)C++ プログラムの基本的な構文の要素: トークン、コメント、演算子、キーワード、区切り記号、リテラル。 また、ファイルの変換、演算子の優先順位/結合規則。

[基本的な概念](../cpp/basic-concepts-cpp.md)スコープ、リンケージ、プログラムの起動と終了、ストレージ クラス、および種類。

[標準変換](../cpp/standard-conversions.md)組み込まれており、または「基本」型どうしの変換を入力します。 また、ポインター、参照、およびメンバーへのポインター型の間の算術変換および変換。

[演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)C++ の演算子。

[式](../cpp/expressions-cpp.md)式のセマンティクスの式の型が演算子やキャスト、キャスト演算子、実行時の型情報のトピックを参照します。

[ラムダ式](../cpp/lambda-expressions-in-cpp.md)プログラミング手法を暗黙的に関数オブジェクト クラスを定義し、そのクラス型の関数オブジェクトを作成します。

[ステートメント](../cpp/statements-cpp.md)式、null、複合、選択、イテレーション、ジャンプ、および宣言ステートメントです。

[宣言と定義](declarations-and-definitions-cpp.md)ストレージ クラス指定子、関数定義、初期化、列挙型、**クラス**、**構造体**、および**共用体**宣言、および**typedef**宣言します。 また、**インライン**関数、 **const**キーワード、名前空間。

[クラス、構造、および共用体](../cpp/classes-and-structs-cpp.md)クラス、構造、および共用体の概要。 また、メンバー関数、特殊なメンバー関数では、データ メンバー、ビット フィールド、**この**ポインター、入れ子になったクラスです。

[派生クラス](../cpp/inheritance-cpp.md)単一および複数の継承、**仮想**関数、複数の基底クラス**抽象**クラス、スコープ規則。 また、 **_ _super**と **_ _interface**キーワード。

[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)クラス メンバーへのアクセス制御:**パブリック**、**プライベート**、および**保護**キーワード。 friend 関数および friend クラス。

[オーバー ロード](operator-overloading.md)オーバー ロードされた演算子、演算子のオーバー ロードの規則。

[例外処理](../cpp/exception-handling-in-visual-cpp.md)C++ 例外処理、構造化例外処理 (SEH)、例外処理ステートメントの記述で使用されるキーワード。

[アサーションと User-Supplied メッセージ](../cpp/assertion-and-user-supplied-messages-cpp.md)
 `#error`ディレクティブ、 **static_assert** 、キーワード、`assert`マクロ。

[テンプレート](../cpp/templates-cpp.md)テンプレートの仕様、関数テンプレート、クラス テンプレート、 **typename**キーワード、テンプレートとマクロ、テンプレートとスマート ポインター。

[イベント処理](../cpp/event-handling.md)イベントとイベント ハンドラーを宣言します。

[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)Microsoft C 固有の修飾子。 メモリをアドレス指定、呼び出し規則、 **naked**関数、拡張ストレージ クラス属性 (**_ _declspec**)、 **_ _w64**します。

[インライン アセンブラー](../assembler/inline/inline-assembler.md)アセンブリ言語および C++ で使用して **_ _asm**ブロックします。

[コンパイラ COM サポート](../cpp/compiler-com-support.md)Microsoft 固有のクラスと COM 型をサポートするために使用されるグローバル関数への参照。

[Microsoft の拡張機能](../cpp/microsoft-extensions.md)C++ に対する Microsoft 拡張機能。

[非標準動作](../cpp/nonstandard-behavior.md)Visual C コンパイラの非標準動作に関する情報。

[C++ へようこそ](welcome-back-to-cpp-modern-cpp.md)最新の C++ プログラミングの概要については、安全な正確で効率的なプログラムの記述のベスト プラクティスです。

## <a name="related-sections"></a>関連項目

[コンポーネントの Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md) Visual C を使用して共通言語ランタイムに対応する資料を参照します。

[C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)コンパイラ オプション、リンカー オプション、およびその他のツールを構築します。

[C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)プラグマ、プリプロセッサ ディレクティブ、定義済みマクロ、およびプリプロセッサに関する資料を参照します。

[Visual C ライブラリ](../standard-library/cpp-standard-library-reference.md)参照へのリンクの一覧は、さまざまな Visual C ライブラリのページを開始します。

## <a name="see-also"></a>関連項目

[C 言語リファレンス](../c-language/c-language-reference.md)
