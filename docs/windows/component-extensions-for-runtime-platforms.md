---
title: Component Extensions for Runtime Platforms |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- what's new [C++], keywords
- what's new [C++], language features
- Visual C++, keywords
- keywords [C++]
- Managed Extensions for C++, replacement syntax
ms.assetid: 1e400ee6-3ac9-4910-a608-9d3d5993e423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c939a2a96d0f8a34dbe9424ab7e07c5a60c2224
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610206"
---
# <a name="component-extensions-for-runtime-platforms"></a>ランタイム プラットフォームのコンポーネントの拡張機能

Visual C++ には、ランタイム プラットフォームに対するプログラミングに役立つ言語拡張が用意されています。 C + を使用して/cli CX、ユニバーサル Windows プラットフォーム アプリとネイティブ コードにコンパイルされるコンポーネントをプログラミングできます。 C + を使用して、Windows ランタイムの COM インターフェイスに対して直接プログラミングしてユニバーサル Windows プラットフォーム アプリを作成できますが、/cli CX、コンス トラクター、例外、およびその他の最新の C++ プログラミングの表現方法で操作することができます。 .NET プラットフォームでマネージ実行環境での C++ プログラミングを有効にするを使用することが C +/cli CLI。

### <a name="two-runtimes-one-set-of-extensions"></a>2 つのランタイムに共通の拡張

C + + CX はサブセットの C++/cli CLI。 拡張機能は共通する C +/cli/CX および C++/cli CLI、セマンティクスが共通言語ランタイム (CLR) または Windows ランタイムを対象にかに依存します。 Windows ランタイムで実行するアプリをコンパイルするには、指定、`/ZW`コンパイラ オプション。 CLR で動作するようにコンパイルする場合は `/clr` コンパイラ オプションを指定します。 Visual Studio を使用してプロジェクトを作成すると、これらのスイッチが自動的に設定されます。

C++ でのユニバーサル Windows プラットフォーム アプリを作成する方法の詳細については、次を参照してください。 [C++ を使用してアプリを Windows ランタイム用のロードマップ](http://msdn.microsoft.com/library/windows/apps/hh700360.aspx)します。

C +/cli CLI は ISO/ANSI C 規格を拡張し、定義下で、Ecma C +/cli CLI 標準。 詳細については、次を参照してください。 [C + での .NET プログラミング/cli (Visual c)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)します。

## <a name="data-type-keywords"></a>データ型のキーワード

言語拡張機能には、*集計キーワード*空白で区切られた 2 つのトークンで構成されるキーワードします。 これらのトークンは、単独で使用した場合と一緒に使用した場合で意味が異なることがあります。 たとえば、"ref" は通常の識別子であり、"class" はネイティブ クラスを宣言するキーワードです。 いますが、フォームにこれらの単語を結合するときに**ref クラス**、結果として得られる集計キーワードと呼ばれるエンティティの宣言を*ランタイム クラス*します。

含めることも、拡張機能*状況に応じた*キーワード。 キーワードが状況依存のキーワードとして扱われるかどうかは、キーワードを含むステートメントの種類と、そのステートメント内でのキーワードの配置で決まります。 たとえば、"property" というトークンは、識別子として使用されることもあれば、特殊なパブリック クラスのメンバーを宣言するために使用されることもあります。

次の表に、C++ 言語拡張のキーワードの一覧を示します。

|キーワード|状況依存|目的|参照|
|-------------|-----------------------|-------------|---------------|
|**ref クラス**<br /><br /> **ref 構造体**|いいえ|クラスを宣言します。|[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)|
|**値クラス**<br /><br /> **値構造体**|いいえ|値クラスを宣言します。|[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)|
|**インターフェイス クラス**<br /><br /> **インターフェイス構造体**|いいえ|インターフェイスを宣言します。|[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)|
|**列挙型クラス**<br /><br /> **列挙型の構造体**|いいえ|列挙型を宣言します。|[列挙型クラス](../windows/enum-class-cpp-component-extensions.md)|
|**プロパティ**|[はい]|プロパティを宣言します。|[プロパティ](../windows/property-cpp-component-extensions.md)|
|**delegate**|[はい]|デリゲートを宣言します。|[delegate (C++ コンポーネント拡張)](../windows/delegate-cpp-component-extensions.md)|
|**event**|[はい]|イベントを宣言します。|[event](../windows/event-cpp-component-extensions.md)|

## <a name="override-specifiers"></a>オーバーライド指定子

次のキーワードは、派生のオーバーライド動作を修飾するために使用できます。 ただし、**新しい**キーワードは C++ の拡張ではなく、追加のコンテキストで使用できるため、ここでは表示されます。 一部の指定子は、ネイティブのプログラミングに対しても有効です。 詳細については、次を参照してください。[方法: オーバーライド指定子を宣言ネイティブ コンパイルで (C +/cli CLI)](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)します。

|キーワード|状況依存|目的|参照|
|-------------|-----------------------|-------------|---------------|
|**abstract**|[はい]|関数またはクラスが抽象型であることを示します。|[abstract](../windows/abstract-cpp-component-extensions.md)|
|**new**|いいえ|関数が基底クラスのバージョンのオーバーライドでないことを示します。|[new (新規スロット vtable の)](../windows/new-new-slot-in-vtable-cpp-component-extensions.md)|
|**override**|[はい]|メソッドが基底クラスのバージョンのオーバーライドでなければならないことを示します。|[override](../windows/override-cpp-component-extensions.md)|
|**sealed**|[はい]|クラスを基底クラスとして使用しないことを示します。|[sealed](../windows/sealed-cpp-component-extensions.md)|

## <a name="keywords-for-generics"></a>ジェネリックのキーワード

ジェネリック型をサポートするために追加されたキーワードを次に示します。 詳細については、「[ジェネリック](../windows/generics-cpp-component-extensions.md)」を参照してください。

|キーワード|状況依存|目的|
|-------------|-----------------------|-------------|
|**汎用**|いいえ|ジェネリック型を宣言します。|
|**where**|[はい]|ジェネリック型パラメーターに適用される制約を指定します。|

## <a name="miscellaneous-keywords"></a>その他のキーワード

C++ 拡張に追加されたその他のキーワードを次に示します。

|キーワード|状況依存|目的|参照|
|-------------|-----------------------|-------------|---------------|
|**finally**|[はい]|例外処理の既定の動作を示します。|[例外処理](../windows/exception-handling-cpp-component-extensions.md)|
|**for each、in**|いいえ|コレクションの要素を列挙します。|[for each、in](../dotnet/for-each-in.md)|
|**gcnew**|いいえ|ガベージ コレクション ヒープに型を割り当てます。 代わりに使用**新しい**と**削除**します。|[ref new、gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**新しい ref**|[はい]|Windows ランタイム型を割り当てます。 代わりに使用**新しい**と**削除**します。|[ref new、gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)|
|**initonly**|[はい]|宣言または静的コンストラクターでしかメンバーを初期化できないことを示します。|[initonly (C++/CLI)](../dotnet/initonly-cpp-cli.md)|
|**リテラル**|[はい]|リテラル変数を作成します。|[リテラル](../windows/literal-cpp-component-extensions.md)|
|**nullptr**|いいえ|ハンドルまたはポインターでオブジェクトを参照しないことを示します。|[nullptr](../windows/nullptr-cpp-component-extensions.md)|

## <a name="template-constructs"></a>テンプレートの構成要素

次の言語構成要素は、キーワードとしてではなく、テンプレートとして実装されています。 `/ZW` コンパイラ オプションを指定した場合は `lang` 名前空間で定義され、 `/clr` コンパイラ オプションを指定した場合は `cli` 名前空間で定義され、

|キーワード|目的|参照|
|-------------|-------------|---------------|
|**array**|配列を宣言します。|[配列](../windows/arrays-cpp-component-extensions.md)|
|**interior_ptr**|(CLR のみ) 参照型でデータを参照します。|[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)|
|**pin_ptr**|(CLR のみ) CLR 参照型を参照して、ガベージ コレクション システムを一時的に無効にします。|[pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)|
|**safe_cast**|ランタイム型の最適なキャスト方法を特定して実行します。|[safe_cast](../windows/safe-cast-cpp-component-extensions.md)|
|**typeid**|(CLR のみ) 指定した型またはオブジェクトを表す <xref:System.Type?displayProperty=fullName> オブジェクトを取得します。|[typeid](../windows/typeid-cpp-component-extensions.md)|

## <a name="declarators"></a>宣言子

割り当てられたオブジェクトの有効期間と削除をランタイムで自動的に管理するように指定する型の宣言子を次に示します。

|演算子|目的|参照|
|--------------|-------------|---------------|
|`^`|オブジェクトを識別するハンドルを宣言します。使用できなくする場合は自動的に削除する Windows ランタイムまたは CLR オブジェクトへのポインターは、します。|[オブジェクト演算子 (^) へのハンドルします。](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)|
|`%`|追跡参照; を宣言します。使用できなくする場合は自動的に削除する Windows ランタイムまたは CLR オブジェクトへの参照は、します。|[参照演算子の追跡](../windows/tracking-reference-operator-cpp-component-extensions.md)|

## <a name="additional-constructs-and-related-topics"></a>その他の構成要素と関連トピック

ここでは、その他のプログラミング構成要素と CLR の関連トピックを示します。

|トピック|説明|
|-----------|-----------------|
|[__identifier (C++/CLI)](../windows/identifier-cpp-cli.md)|(Windows ランタイムと CLR)識別子としてのキーワードを使用できるようにします。|
|[可変個引数リスト (...) (C++/CLI)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)|(Windows ランタイムと CLR)可変個の引数を実行する関数を使用できます。|
|[C++ ネイティブ型と等価な .NET Framework ネイティブ型 (C++/CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)|C++ の整数型の代わりに使用される CLR 型を示します。|
|[appdomain](../cpp/appdomain.md) **_ _declspec**修飾子|**_ _declspec** appdomain ごとに静的変数とグローバル変数が存在するよう指示する修飾子。|
|[C スタイル キャストと/clr (C +/cli CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)|C スタイル キャストがどのように解釈されるかについて説明します。|
|[_ _clrcall](../cpp/clrcall.md)呼び出し規約|CLR 準拠の呼び出し規則を示します。|
|`__cplusplus_cli`|[定義済みマクロ](../preprocessor/predefined-macros.md)|
|[カスタム属性](../windows/custom-attributes-cpp.md)|独自の CLR 属性を定義する方法について説明します。|
|[例外処理](../windows/exception-handling-cpp-component-extensions.md)|例外処理の概要を示します。|
|[明示的なオーバーライド](../windows/explicit-overrides-cpp-component-extensions.md)|メンバー関数で任意のメンバーをオーバーライドする方法を示します。|
|[フレンド アセンブリ (C++)](../dotnet/friend-assemblies-cpp.md)|クライアント アセンブリでアセンブリ コンポーネントのすべての型にアクセスする方法について説明します。|
|[ボックス化](../windows/boxing-cpp-component-extensions.md)|値型がボックス化される条件を示します。|
|[型の特徴のコンパイラ サポート](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)|コンパイル時に型の特性を検出する方法について説明します。|
|[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)プラグマ|同じモジュールにマネージド 関数とアンマネージド 関数を共存させる方法を示します。|
|[プロセス](../cpp/process.md) **_ _declspec**修飾子|**_ _declspec**プロセスごとに静的変数とグローバル変数が存在するよう指示する修飾子。|
|[リフレクションの問題 (C++/CLI)](../dotnet/reflection-cpp-cli.md)|CLR バージョンのランタイム型情報を示します。|
|[String](../windows/string-cpp-component-extensions.md)|文字列リテラルから <xref:System.String> へのコンパイラによる変換について説明します。|
|[型の転送 (C++/CLI)](../windows/type-forwarding-cpp-cli.md)|クライアント コードを再コンパイルしなくても済むように、出荷時のアセンブリの型を別のアセンブリに移動できるようにします。|
|[ユーザー定義の属性](../windows/user-defined-attributes-cpp-component-extensions.md)|ユーザー定義の属性を示します。|
|[#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)|外部アセンブリをインポートします。|
|[XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)|使用して XML ベースのコード ドキュメントについて説明します[/doc (ドキュメント コメントの処理) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)|

## <a name="see-also"></a>関連項目

[C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
[ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)