---
title: 既定で無効になっているコンパイラ警告 |Microsoft ドキュメント
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d311c730781aee70d4b77723ddec98a79407e42a
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705567"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>既定で無効になっているコンパイラの警告

コンパイラには、それらを表示するほとんどの開発者が必要ないために、既定では、オフになっている警告が含まれます。 場合によっては、以前のコードに共通の表現方法は、または言語への Microsoft 拡張機能の利用、デザインの選択肢を表現します。 それ以外の場合、これらは、領域をプログラマが多くの場合、予期しない、または未定義の動作が生じる可能性がありますの不適切な想定を行う場所を示します。 これらの警告のいくつかは、ライブラリのヘッダーでは、非常にノイズ可能性があります。 C ランタイム ライブラリおよび C++ 標準ライブラリは、警告レベルでのみ警告を発するありません[/W4](../build/reference/compiler-option-warning-level.md)です。

## <a name="enable-warnings-that-are-off-by-default"></a>既定で無効になっている警告を有効にします。

無効になっている通常既定では、次のオプションのいずれかを使用して警告を有効にすることができます。

- **#pragma 警告 (既定:** *warning_number* **)**

   指定された警告 (*warning_number*) が既定のレベルで有効になっています。 警告に関するドキュメントには、既定のレベルの警告が記載されています。

- **#pragma warning(** *warning_level* **:** *warning_number* **)**

   指定された警告 (*warning_number*) が、指定されたレベルで有効な (*warning_level*)。

- [/Wall](../build/reference/compiler-option-warning-level.md)

   **/壁**既定で無効になっているすべての警告を有効にします。 使用して個々 の警告をオフにすることができます、このオプションを使用する場合、 [/wd](../build/reference/compiler-option-warning-level.md)オプション。

- [/w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   これにより、警告*nnnn*レベルで*L*です。

## <a name="warnings-that-are-off-by-default"></a>既定で無効になっている警告

次の警告は、Visual Studio 2015 およびそれ以降のバージョンで既定では無効になります。

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (レベル 4)|列挙子 '*識別子*'で列挙型の switch'*列挙*' は case ラベルによって明示的にハンドルされません|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (レベル 4)|列挙子 '*識別子*'で列挙型の switch'*列挙*' はハンドルされません|
|C4191 (レベル 3)|'*演算子*': 安全でない変換から'*type_of_expression*'to'*type_required*'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (レベル 4)|'*識別子*': から変換'*type1*'to'*type2*'、データ損失の可能性|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (レベル 4)|'*演算子*': から変換'*type1*'to'*type2*'、データ損失の可能性|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (レベル 4)|'*関数*': 関数プロトタイプがありません: '()' を '(void)' を変換します。|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (レベル 4)|'*関数*': メンバー関数はどの基底クラス仮想メンバー関数をオーバーライドしません|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (レベル 1)|'*virtual_function*': ベースから仮想メンバー関数の使用可能なオーバーライドはありません'*クラス*' です関数は隠されます。|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (レベル 3)|'*クラス*': クラスは仮想関数を含んでいますが、デストラクターが仮想ではありません。|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (レベル 4)|'*関数*': ベースから仮想メンバー関数の使用可能なオーバーライドはありません'*型*' です関数は隠されます。|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (レベル 3)|'*演算子*': 符号なし/負の定数が一致しません|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (レベル 4)|使用される標準の拡張機能: '*var*': for ループ スコープの外側のループで宣言したループ コントロール変数が使用します。|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (レベル 4)|'*演算子*': 式は常に false|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (レベル 4)|'*型*': 未定義の型の使用が CLR meta-data で検出されたこの型の使用は、ランタイム例外する可能性があります|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (レベル 1)|動作変更: '*関数*' 呼び出されると、メンバー演算子が以前のバージョンで呼び出されましたが、|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (レベル 1)|動作変更: '*member1*'の代わりと呼ばれる'*member2*'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : ベース メンバー初期化リストで使用されました。|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (レベル 4)|'*アクション*': から変換'*type_1*'to'*type_2*'、符号付き/符号なしの不一致|
|C4370 (レベル 3)|パッキングの改善のために、前バージョンのコンパイラからクラスのレイアウトが変更されました。|
|[C4371](../error-messages/compiler-warnings/c4371.md) (レベル 3)|'*classname*': クラスのレイアウトは、メンバーのパッキングの改善のため、コンパイラの以前のバージョンから変更された可能性があります'*メンバー*'|
|C4388 (レベル 4)|signed と unsigned の数値を比較しようとしました。|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (レベル 2)|'*関数*': 関数のシグネチャには、型が含まれています'*型*';。C++ オブジェクトは、純粋なコードの間で受け渡すに安全でないと混合またはネイティブ|
|C4426 (レベル 1)|#pragma optimize() による最適化フラグがヘッダーを含めた後に変更された可能性があります<sup>14.1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (レベル 4)|'*class1*':/vd2 下のオブジェクトのレイアウトは仮想ベースにより変更されます'*class2*'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (レベル 4)|仮想基本から dynamic_cast '*class1*'to'*class2*' 一部のコンテキストで失敗する可能性があります|
|C4444 (レベル 3)|トップ レベルの '__unaligned' がこのコンテキストで実装されていません。|
|[C4464](../error-messages/compiler-warnings/c4464.md) (レベル 4)|相対インクルード パスを含む '.. '|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (レベル 4)|対象範囲外の列挙の事前宣言が基になる型 (int が想定されます) を持つ必要があります<sup>Perm</sup>|
|C4472 (レベル 1)|'*識別子*' ネイティブ列挙型は、: マネージ列挙型を宣言するアクセス指定子 (プライベート/パブリック) の追加|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (レベル 4)|'*関数*': 参照されていないインライン関数は削除されました|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (レベル 4)|'type name': 型名のメタデータの限度を超えています '*制限*' 文字。|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (レベル 1)|コンマ前の式は、引数リストのない関数として評価します。|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (レベル 1)|コンマの前の関数呼び出しに引数一覧がありません。|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (レベル 1)|'*演算子*': コンマも何も起こりません前の演算子の副作用が必要な演算子。|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (レベル 1)|コンマ前の式は無効です。有効な式を指定してください。|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (レベル 1)|'*operator1*': コンマの前に、の演算子も何も起こりませんするつもりでした'*operator2*' しますか?。|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (レベル 1)|式の影響はありません; 式の副作用が必要です。|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (レベル 3)|'_ _assume' には、影響が含んでいます '*効果*'。|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (レベル 4)|Visual C 7.1; から変更情報: catch (...) セマンティクス構造化例外 (SEH) はキャッチされません。|
|C4574 (レベル 4)|'*識別子*'として定義されている' 0': を使用する意味する '#if*識別子*' しますか?|
|C4577 (レベル 1)|' noexcept' がない例外です。 指定されたモードを処理で使用例外で終了処理は保証されません。 /EHsc を指定してください。|
|C4582 (レベル 4)|'*型*': コンス トラクターは暗黙的に呼び出されません|
|C4583 (レベル 4)|'*型*': デストラクターは暗黙的に呼び出されません|
|C4587 (レベル 1)|'*anonymous_structure*': 動作変更: コンス トラクターが不要になった暗黙的に呼び出されます|
|C4588 (レベル 1)|'*anonymous_structure*': 動作変更: デストラクターは呼び出されなく|
|C4596 (レベル 4)|'*識別子*': メンバー宣言で無効な修飾名<sup>14.3</sup> <sup>Perm</sup>|
|C4598 (レベル 1 およびレベル 3)|' #include"*ヘッダー*"': ヘッダー番号*数*プリコンパイル済みヘッダーと一致しませんその位置にある現在のコンパイル<sup>14.3</sup>|
|C4599 (レベル 3)|'*オプション**パス*': コマンドライン引数の数*数*プリコンパイル済みヘッダーと一致しません<sup>14.3</sup>|
|C4605 (レベル 1)|'/D*マクロ*' 現在のコマンドラインで指定したが、プリコンパイル済みヘッダーがビルドされたが指定されていません|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (レベル 3)|'*union_member*'は既に初期化されて、初期化子リストで別の共用体メンバーにより'*union_member*' <sup>Perm</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (レベル 3)|#pragma warning: 警告番号がありません '*数*'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (レベル 4)|'derived class': 基底クラスの既定コンストラクターにアクセスできないため、既定のコンストラクターは生成できませんでした。|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (レベル 4)|'derived class': 基底クラスのコピー コンストラクターにアクセスできないため、コピー コンストラクターは生成できませんでした。|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (レベル 4)|'derived class': 基底クラスの代入演算子にアクセスできないため、代入演算子は生成できませんでした。|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (レベル 1)|digraphs は -Ze でサポートされていません。 文字のシーケンス '*digraph*'の代替トークンとして解釈されません'*char*'。|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (レベル 3)|'*インスタンス*': ローカル スタティック オブジェクトの構築がスレッド セーフではありません|
|C4647 (レベル 3)|動作変更: _ _is_pod (*型*) 別の値が、以前のバージョン|
|C4654 (レベル 4)|プリコンパイル済みヘッダーの前に配置されたコードは、行は無視されます。 コードをプリコンパイル済みヘッダーに追加します。 <sup>14.1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (レベル 4)|'*シンボル*'が '0' に置換するプリプロセッサ マクロとして定義されていません'*ディレクティブ*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (レベル 4)|'*シンボル*': 方向性のあるパラメーター属性がいません指定すると、[入力]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (レベル 3)|'*ユーザー定義型*': 動作の変更可能な UDT の戻り値呼び出し規約|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (レベル 1)|'*関数*': 公開されたメンバーのシグネチャはアセンブリ プライベート ネイティブ型を含む'*native_type*'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (レベル 4)|'*関数*': 関数のインライン関数ではありません|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (レベル 3)|メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|揮発性アクセス '*式*' は/volatile:\<iso&#124;ms > 設定; _iso_volatile_load/store 組み込み関数の使用を検討してください|
|C4749 (レベル 4)|条件付きでサポートされる: non standard レイアウトの種類に適用される offsetof '*型*'|
|C4767 (レベル 4)|セクション名 '*シンボル*' が 8 文字より長いと、リンカーによって切り詰められます|
|C4768 (レベル 3)|リンケージ指定する前に _ _declspec 属性は無視されます。|
|C4774 (レベル 4)|'*文字列*': 書式指定文字列の引数で予期されて*数*はない文字列リテラル|
|C4777 (レベル 4)|'*関数*': 書式文字列'*文字列*'型の引数が必要です'*type1*'、可変個引数が、*数*型を持つ '*type2*'|
|C4786 (レベル 3)|'*シンボル*': オブジェクトの名前は切り詰められました'*数*' 文字にデバッグ情報で|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (レベル 4)|'*バイト*'構築後に追加されたバイトのパディング'*member_name*'|
|C4826 (レベル 2)|変換 '*type1*'to'*type2*' を符号拡張します。 これにより、予期しない実行時の動作が発生する可能性があります。|
|C4837 (レベル 4)|トライグラフが検出されました: ' [概要] タブ*文字*'置き換え'*文字*'|
|C4841 (レベル 4)|使用する標準の拡張機能: offsetof で使用される複合メンバーの指定子|
|C4842 (レベル 4)|コンパイラのリリース間で一致するように 'offsetof' の複数の継承を使用して型に適用の結果は保証されません。|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (レベル 4)|'_ファイル_(*line_number*)' コンパイラは、中かっこで囲んだ初期化リスト内で左から右へ評価順序を強制いない可能性があります|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (レベル 1)|'LPSTR' にキャストされた幅の広いリテラル文字列|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (レベル 1)|'LPWSTR' にキャストされたリテラル文字列|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (レベル 1)|'*宣言子*': GUID 関連付けることができますのみクラス、インターフェイス、または名前空間|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (レベル 1)|コピー初期化が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (レベル 4)|number ビット ポインター用にタイプ ライブラリがビルドされていることを想定します。|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (レベル 1)|reinterpret_cast が関連クラス間で使用されました: '*class1*'および'*class2*'|
|C4962|'*関数*': プロファイル ガイド付き最適化の最適化によってプロファイル データに矛盾が生じたために使用できません|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (レベル 4)|'*シンボル*': 例外の指定が前の宣言と一致しません|
|C4987 (レベル 4)|非標準の拡張機能が使用されています: 'throw (...)' です。|
|C4988 (レベル 4)|'*シンボル*': 変数には、外側のクラス/関数スコープが宣言されています|
|C5022|'*型*': 指定された複数の移動コンス トラクター|
|C5023|'*型*': 指定された複数の移動代入演算子|
|C5024 (レベル 4)|'*型*': 移動コンス トラクターが暗黙的に削除済みとして定義|
|C5025 (レベル 4)|'*型*': 移動代入演算子が暗黙的に削除済みとして定義|
|C5026 (レベル 1 およびレベル 4)|'*型*': 移動コンス トラクターが暗黙的に削除済みとして定義|
|C5027 (レベル 1 およびレベル 4)|'*型*': 移動代入演算子が暗黙的に削除済みとして定義|
|C5029 (レベル 4)|使用される標準の拡張機能: C++ のアラインメント属性は、変数、データ メンバーおよびタグの種類のみに適用|
|C5031 (レベル 4)|#pragma warning (pop): ポップの警告状態の別のファイルにプッシュされた可能性が高い不一致<sup>14.1</sup>|
|C5032 (レベル 4)|いない対応する #pragma warning (pop) と #pragma warning (push) が検出<sup>14.1</sup>|
|C5034|組み込みの使用 '*組み込み*' 関数*関数*ゲスト コードとしてコンパイルする<sup>15.3</sup>|
|C5035|機能の使用 '*機能*' 関数*関数*ゲスト コードとしてコンパイルする<sup>15.3</sup>|
|C5036 (レベル 1)|/hybrid:x86arm64 でコンパイルすると、varargs 関数へのポインター変換 '*type1*'to'*type2*' <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (レベル 4)|データ メンバー '*member1*'データ メンバーの後に初期化されます'*member2*' <sup>15.3</sup>|
|C5039 (レベル 4)|'*関数*': - EHc に基づいて、extern C 関数に渡される可能性のある関数のスローに対するポインターまたは参照します。 未定義の動作は、この関数が例外をスローした場合に発生する可能性があります。 <sup>15.5</sup>|
|C5042 (レベル 3)|'*関数*': ブロック スコープでの関数宣言は、C++ の標準で指定された 'inline' をすることはできません 'inline' 指定子を削除<sup>15.5。</sup>|

<sup>14.1</sup>この警告は Visual Studio 2015 Update 1 以降使用できます。<br>
<sup>14.3</sup>この警告は Visual Studio 2015 Update 3 以降使用できます。<br>
<sup>15.3</sup>この警告は、Visual Studio 2017 15.3 のバージョンので利用可能です。<br>
<sup>15.5</sup>この警告は、Visual Studio 2017 15.5 のバージョンので利用可能です。<br>
<sup>Perm</sup>この警告はオフになっていない限り、[寛容/-](../build/reference/permissive-standards-conformance.md)コンパイラ オプションを設定します。

## <a name="warnings-off-by-default-in-earlier-versions"></a>以前のバージョンで既定でオフの警告

これらの警告は、Visual Studio 2015 の前に、コンパイラのバージョンでは既定でオフしました。

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (レベル 2)|'*変換*': から切り捨て'*type1*'to'*type2*'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (レベル 1)|'*変数*': ポインターから切り詰めます'*型*'to'*型*'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (レベル 1)|'*操作*': から変換'*type1*'to'*type2*' より大きいサイズの|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (レベル 1)|'*演算子*': ゼロ拡張'*type1*'to'*type2*' より大きいサイズの|

この警告は、Visual Studio 2012 より前に、コンパイラのバージョンでは既定でオフしました。

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (レベル 4)|型指定子がありません - int と仮定しました。 メモ: C は、現在 int を既定値としてサポートしていません|

## <a name="see-also"></a>関連項目

[warning](../preprocessor/warning.md)
