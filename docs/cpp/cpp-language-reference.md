---
title: C++ 言語リファレンス |Microsoft ドキュメント
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
ms.openlocfilehash: 25315121d3004601914c5b8872b496e57acec99f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417204"
---
# <a name="c-language-reference"></a>C++ 言語リファレンス
このリファレンスでは、Microsoft Visual C++ に実装されている C++ プログラミング言語について説明します。 この体系は、Margaret Ellis と Bjarne Stroustrup による*Annotated C++ Reference Manual* および ANSI/ISO C++ 国際規格 (ISO/IEC FDIS 14882) に基づいてます。 Microsoft 固有の C++ 言語機能の実装も含まれます。  

最新の C++ プログラミングの概要については、次を参照してください。[C++ へようこそ](welcome-back-to-cpp-modern-cpp.md)に戻ってください。
  
 キーワードまたは演算子をすばやく見つけるには、次の表を参照してください。  
  
-   [C++ のキーワード](../cpp/keywords-cpp.md)  
  
-   [C++ 演算子](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
  
## <a name="in-this-section"></a>このセクションの内容  

 [構文規則](../cpp/lexical-conventions.md)  
 C++ プログラムの基本的な構文の要素: トークン、コメント、演算子、キーワード、区切り記号、リテラル。 また、ファイルの変換、演算子の優先順位/結合規則。  
  
 [基本的な概念](../cpp/basic-concepts-cpp.md)  
 スコープ、リンケージ、プログラムの起動と終了、ストレージ クラス、および型。  
  
 [標準変換](../cpp/standard-conversions.md)  
 組み込み型 (基本型) 間の型変換。 また、ポインター、参照、およびメンバーへのポインター型の間の算術変換および変換。  
  
 [演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)  
 C++ 言語の演算子。  
  
 [式](../cpp/expressions-cpp.md)  
 式の型とセマンティクス、演算子の参照トピック、キャスト演算子、実行時の型情報。  
  
 [ラムダ式](../cpp/lambda-expressions-in-cpp.md)  
 暗黙的に関数オブジェクト クラスを定義し、そのクラス型の関数オブジェクトを生成するプログラミング手法。  
  
 [ステートメント](../cpp/statements-cpp.md)  
 式、NULL、複合、選択、イテレーション、ジャンプ、および宣言ステートメント。  
  
 [宣言と定義](declarations-and-definitions-cpp.md)  
 ストレージ クラス指定子、関数定義、初期化、列挙体、クラス宣言、構造体宣言、および共用体宣言、および typedef 宣言。 また、インライン関数、定数のキーワード、名前空間。  
  
 [宣言子](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)  
 オブジェクト、型、または関数の名前を指定する宣言ステートメントの要素。 抽象宣言子、型名、初期化子、関数宣言と定義、配列、参照。  
  
 [クラス、構造、および共用体](../cpp/classes-and-structs-cpp.md)  
 クラス、構造体、および共用体の概要。 また、メンバー関数、特殊なメンバー関数、データ メンバー、ビット フィールド、このポインター、入れ子になったクラス。  
  
 [派生クラス](../cpp/inheritance-cpp.md)  
 単一継承と多重継承、仮想関数、複数の基底クラス、抽象クラス、スコープ規則。 また、__super および \__interface キーワード。  
  
 [メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)  
 クラス メンバーへのアクセスの制御: public、private、および protected キーワード。 friend 関数および friend クラス。  
  
 [オーバー ロード](operator-overloading.md)  
 オーバー ロードされた演算子、演算子のオーバー ロードの規則。  
  
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)  
 例外処理ステートメントの記述に使用される C++ 例外処理、構造化例外処理 (SEH)、キーワード。  
  
 [アサーションとユーザー指定のメッセージ](../cpp/assertion-and-user-supplied-messages-cpp.md)  
 `#error` ディレクティブ、`static_assert` キーワード、`assert` マクロ。  
  
 [テンプレート](../cpp/templates-cpp.md)  
 テンプレートの仕様、関数テンプレート、クラス テンプレート、typename キーワード、テンプレートとマクロの比較、テンプレート、スマート ポインター。  
  
 [イベント処理](../cpp/event-handling.md)  
 イベントとイベント ハンドラーの宣言。  
  
 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)  
 Microsoft C++ 固有の修飾子。 メモリのアドレス指定、呼び出し規約、naked 関数、拡張ストレージクラス属性 (__declspec)、 \__w64。  
  
 [インライン アセンブラー](../assembler/inline/inline-assembler.md)  
 __asm ブロックでのアセンブリ言語と C++ の使用。  
  
 [コンパイラ COM サポート](../cpp/compiler-com-support.md)  
 COM 型をサポートするために使用する Microsoft 固有のクラスとグローバル関数への参照。  
  
 [Microsoft 拡張機能](../cpp/microsoft-extensions.md)  
 C++ の Microsoft 拡張機能。  
  
 [非標準動作](../cpp/nonstandard-behavior.md)  
 Visual C++ コンパイラの非標準動作に関する情報。  

 [C++ へようこそ](welcome-back-to-cpp-modern-cpp.md)プラクティス セーフである、正確で効率的なプログラムを記述するための最新の C++ プログラミングの概要です。
  
## <a name="related-sections"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)  
 共通言語ランタイムを対象とするための Visual C++ の使用に関するリファレンス資料。  
  
 [C/C++ ビルドのリファレンス](../build/reference/c-cpp-building-reference.md)  
 コンパイラ オプション、リンカー オプション、およびその他のビルド ツール。  
  
 [C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)  
 プラグマ、プリプロセッサ ディレクティブ、定義済みマクロ、およびプリプロセッサに関するリファレンス資料。  
  
 [Visual C++ ライブラリ](../standard-library/cpp-standard-library-reference.md)  
 Visual C++ のさまざまなライブラリの参照のスタート ページへのリンクの一覧。  
  
## <a name="see-also"></a>関連項目  
 [C 言語リファレンス](../c-language/c-language-reference.md)