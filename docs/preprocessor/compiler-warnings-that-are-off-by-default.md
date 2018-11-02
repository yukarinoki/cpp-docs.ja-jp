---
title: 既定で無効になっているコンパイラ警告
ms.date: 05/30/2018
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
ms.openlocfilehash: 48c18ce5af758e1329f149bc49969dad733af88f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651374"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>既定で無効になっているコンパイラの警告
コンパイラには、ほとんどの開発者は、それらを表示したくありませんので、既定でオフになっている警告が含まれます。 場合によっては、古いコードは、一般的なイディオムにあるまたは言語から、Microsoft 拡張機能の利用、スタイル上の選択肢を表現します。 それ以外の場合でプログラマは予期されない、または未定義の動作につながる可能性がありますが、誤った仮定で動作を行う多くの場合、領域を示します。 これらの警告の一部は、ライブラリのヘッダーで非常にノイズの多い可能性があります。 C ランタイム ライブラリと C++ 標準ライブラリは、警告レベルでのみ警告を発するありません[/W4](../build/reference/compiler-option-warning-level.md)します。

## <a name="enable-warnings-that-are-off-by-default"></a>既定で無効になっている警告を有効にします。

無効になっている通常既定では、次のオプションのいずれかを使用して警告を有効にできます。

- **#pragma 警告 (既定:** *warning_number* **)**

   指定の警告 (*warning_number*) が既定のレベルで有効になっています。 警告に関するドキュメントには、既定のレベルの警告が記載されています。

- **#pragma warning(** *warning_level* **:** *warning_number* **)**

   指定の警告 (*warning_number*) は、指定されたレベルで有効になっている (*warning_level*)。

- [/Wall](../build/reference/compiler-option-warning-level.md)

   `/Wall` は既定では無効のすべての警告を有効にします。 使用して個々 の警告をオフにすることができます、このオプションを使用する場合、 [/wd](../build/reference/compiler-option-warning-level.md)オプション。

- [/w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   これにより、警告*nnnn*レベル*L*します。

## <a name="warnings-that-are-off-by-default"></a>既定で無効になっている警告

次の警告は、Visual Studio 2015 以降で既定でオフには。

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (レベル 4)|列挙子 '*識別子*列挙型のスイッチ' で'*列挙*' case ラベルによって明示的に処理されません。|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (レベル 4)|列挙子 '*識別子*列挙型のスイッチ' で'*列挙*' はハンドルされません|
|C4191 (レベル 3)|'*演算子*': 安全でない変換から'*type_of_expression*'to'*type_required*'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (レベル 4)|'*識別子*': から変換'*type1*'to'*type2*'、データ損失の可能性|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (レベル 4)|'*演算子*': から変換'*type1*'to'*type2*'、データ損失の可能性|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (レベル 4)|'*関数*': 関数プロトタイプがありません: '()' を '(void)' に変換します。|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (レベル 4)|'*関数*': メンバー関数はどの基底クラス仮想メンバー関数をオーバーライドしません|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (レベル 1)|'*virtual_function*': ベースからの仮想メンバー関数用のオーバーライドはありません'*クラス*'; 関数が非表示|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (レベル 3)|'*クラス*': クラスは仮想関数を含んでいますが、デストラクターが仮想ではありません。|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (レベル 4)|'*関数*': ベースからの仮想メンバー関数用のオーバーライドはありません'*型*'; 関数が非表示|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (レベル 3)|'*演算子*': 符号なし/負の定数が一致しません|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (レベル 4)|標準の拡張機能を使用します '*var*': for ループで宣言したループ コントロール変数が for ループ スコープの外側で使用。|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (レベル 4)|'*演算子*': 式は常に false|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (レベル 4)|'*型*': 未定義の型の使用が CLR meta-data で検出されましたこの型を使用して、ランタイム例外が生じる|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (レベル 1)|動作変更: '*関数*' 呼び出されると、メンバー演算子が以前のバージョンで呼び出されましたが、|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (レベル 1)|動作変更: '*member1*'の代わりに呼び出す'*member2*'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : ベース メンバー初期化リストで使用されました。|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (レベル 4)|'*アクション*': から変換'*type_1*'to'*type_2*'、signed/unsigned が一致しません|
|C4370 (レベル 3)|パッキングの改善のために、前バージョンのコンパイラからクラスのレイアウトが変更されました。|
|[C4371](../error-messages/compiler-warnings/c4371.md) (レベル 3)|'*classname*': クラスのレイアウトは、メンバーのパッキングの改善のため、コンパイラの以前のバージョンから変更された可能性があります'*メンバー*'|
|C4388 (レベル 4)|signed と unsigned の数値を比較しようとしました。|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (レベル 2)|'*関数*': 関数のシグネチャには、型が含まれています'*型*';。C++ のオブジェクトは純粋なコードの間で渡すため安全でないと混合またはネイティブ|
|C4426 (レベル 1)|#pragma optimize() が原因で最適化フラグがヘッダーを含めた後に変更があります<sup>14.1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (レベル 4)|'*class1*':/vd2 下のオブジェクトのレイアウトは仮想ベースにより変更されます'*class2*'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (レベル 4)|仮想基本から dynamic_cast '*class1*'to'*class2*' 一部のコンテキストで失敗する可能性があります|
|C4444 (レベル 3)|トップ レベルの '__unaligned' がこのコンテキストで実装されていません。|
|[C4464](../error-messages/compiler-warnings/c4464.md) (レベル 4)|相対インクルード パスを含む '… '|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (レベル 4)|スコープを持たない列挙型の事前宣言は、基になる型 (int が想定されます) をいる必要があります<sup>Perm</sup>|
|C4472 (レベル 1)|'*識別子*' はネイティブ列挙型: マネージ列挙型を宣言するアクセス指定子 (秘密/公開) の追加|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (レベル 4)|'*関数*': 参照されていないインライン関数は削除されました|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (レベル 4)|'type name': 型名では、メタ データの上限を超えています '*制限*' 文字。|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (レベル 1)|コンマ前の式は、引数リストのない関数として評価します。|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (レベル 1)|コンマの前の関数呼び出しに引数一覧がありません。|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (レベル 1)|'*演算子*': コンマも何も起こりません前の演算子の副作用が予想される演算子。|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (レベル 1)|コンマ前の式は無効です。有効な式を指定してください。|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (レベル 1)|'*operator1*': コンマの前に、の演算子は無効です。 つもりでした'*operator2*' でしょうか。|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (レベル 1)|式の影響はありません; 式の副作用が必要です。|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (レベル 3)|効果を含む '_assume' '*効果*'|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (レベル 4)|情報: catch (...) セマンティクスが Visual C 7.1; から変更構造化例外 (SEH) はキャッチされません。|
|C4574 (レベル 4)|'*識別子*'は' 0': 候補を使用して、' #if*識別子*' でしょうか。|
|C4577 (レベル 1)|' noexcept' の処理モードが指定されていない例外の併用例外で終了処理は保証されません。 /EHsc を指定します。|
|C4582 (レベル 4)|'*型*': コンス トラクターが暗黙的に呼び出されません|
|C4583 (レベル 4)|'*型*': デストラクターは暗黙的に呼び出されません|
|C4587 (レベル 1)|'*anonymous_structure*': 動作変更: コンス トラクターが不要になった暗黙的に呼び出されます|
|C4588 (レベル 1)|'*anonymous_structure*': 動作変更: デストラクターは呼び出されなく|
|C4596 (レベル 4)|'*識別子*': メンバー宣言での無効な修飾名<sup>14.3</sup> <sup>Perm</sup>|
|C4598 (レベル 1 およびレベル 3)|' #include"*ヘッダー*"' ヘッダー番号*数*、プリコンパイル済みヘッダーと一致しませんその位置にある現在のコンパイル<sup>14.3。</sup>|
|C4599 (レベル 3)|'*オプション**パス*': コマンドライン引数の数*数*プリコンパイル済みヘッダーと一致しません<sup>14.3</sup>|
|C4605 (レベル 1)|'/D*マクロ*' 現在のコマンドラインで指定しますが、プリコンパイル済みヘッダーを構築したときに指定されませんでした|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (レベル 3)|'*union_member*'は既に初期化されて、初期化子リストで、もう 1 つの共用体メンバーにより'*union_member*' <sup>Perm</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (レベル 3)|#pragma warning: 警告番号がありません '*数*'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (レベル 4)|'derived class': 基底クラスの既定コンストラクターにアクセスできないため、既定のコンストラクターは生成できませんでした。|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (レベル 4)|'derived class': 基底クラスのコピー コンストラクターにアクセスできないため、コピー コンストラクターは生成できませんでした。|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (レベル 4)|'derived class': 基底クラスの代入演算子にアクセスできないため、代入演算子は生成できませんでした。|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (レベル 1)|digraphs は -Ze でサポートされていません。 文字のシーケンス '*digraph*'の代替トークンとして解釈されない'*char*'|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (レベル 3)|'*インスタンス*': ローカル スタティック オブジェクトの構築がスレッド セーフではありません|
|C4647 (レベル 3)|動作変更: _ _is_pod (*型*) 別の値が、以前のバージョン|
|C4654 (レベル 4)|プリコンパイル済みヘッダーの前に配置されたコードは、行が無視されます。 コードをプリコンパイル済みヘッダーに追加します。 <sup>14.1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (レベル 4)|'*シンボル*'は '0' に置き換える、プリプロセッサ マクロとして定義されていない'*ディレクティブ*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (レベル 4)|'*シンボル*': 方向性のあるパラメーター属性がいません指定すると、[in]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (レベル 3)|'*ユーザー定義型*': 動作の変更可能な UDT の戻り値の呼び出し規則|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (レベル 1)|'*関数*': 公開されたメンバーのシグネチャはアセンブリ プライベート ネイティブ型を含む'*native_type*'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (レベル 4)|'*関数*': 関数のインライン化できません|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (レベル 3)|メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|揮発性アクセス '*式*' は/volatile:\<iso&#124;ms > 設定; _iso_volatile_load/store 組み込み関数を使用を検討してください|
|C4749 (レベル 4)|条件付きでサポートされています: 非標準レイアウト型に適用される offsetof '*型*'|
|C4767 (レベル 4)|セクション名 '*シンボル*' が 8 文字より長いと、リンカーによって切り詰められます|
|C4768 (レベル 3)|リンケージ指定の前に _ _declspec 属性は無視されます。|
|C4774 (レベル 4)|'*文字列*': 書式指定文字列の引数で想定される*数*リテラル文字列はありません|
|C4777 (レベル 4)|'*関数*': 書式文字列'*文字列*'型の引数が必要です'*type1*'、可変個引数が、*数*型が '*type2*'|
|C4786 (レベル 3)|'*シンボル*': オブジェクト名は切り詰められました'*数*' 文字にデバッグ情報で|
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (レベル 4)|'*バイト*"構築後に追加されたバイトのパディング"*member_name*'|
|C4826 (レベル 2)|変換 '*type1*'to'*type2*' は符号拡張します。 これにより、予期しない実行時の動作が発生する可能性があります。|
|C4837 (レベル 4)|検出されたトライグラフ: '??*文字*'置き換え'*文字*'|
|C4841 (レベル 4)|非標準の拡張機能が使用: 複合メンバー指定子が offsetof で使用されます。|
|C4842 (レベル 4)|'offsetof' の複数の継承を使用して、型に適用の結果は、コンパイラ リリース間において一貫性は保証されません。|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (レベル 4)|'_ファイル_(*line_number*)' コンパイラは、中かっこで囲んだ初期化リスト内で左から右の評価順序を強制しない可能性があります|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (レベル 1)|'LPSTR' にキャストされた幅の広いリテラル文字列|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (レベル 1)|'LPWSTR' にキャストされたリテラル文字列|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (レベル 1)|'*宣言子*': GUID はクラス、インターフェイス、または名前空間に関連付けできます。|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (レベル 1)|コピー初期化が正しくありません。複数のユーザー定義の変換が暗黙的に適用されています。|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (レベル 4)|number ビット ポインター用にタイプ ライブラリがビルドされていることを想定します。|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (レベル 1)|reinterpret_cast が関連クラス間で使用されました: '*class1*'と'*class2*'|
|C4962|'*関数*': プロファイル ガイド付き最適化の最適化によってプロファイル データに矛盾が生じたために無効です|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (レベル 4)|'*シンボル*': 例外の指定が以前の宣言と一致しません|
|C4987 (レベル 4)|非標準の拡張機能が使用されています: 'throw (...)' です。|
|C4988 (レベル 4)|'*シンボル*': 変数には、外側のクラス/関数スコープが宣言されています|
|C5022|'*型*': 指定された複数の移動コンス トラクター|
|C5023|'*型*': 指定された複数の移動代入演算子|
|C5024 (レベル 4)|'*型*': 移動コンス トラクターが暗黙的に削除済みとして定義|
|C5025 (レベル 4)|'*型*': 移動代入演算子が暗黙的に削除済みとして定義|
|C5026 (レベル 1 およびレベル 4)|'*型*': 移動コンス トラクターが暗黙的に削除済みとして定義|
|C5027 (レベル 1 およびレベル 4)|'*型*': 移動代入演算子が暗黙的に削除済みとして定義|
|C5029 (レベル 4)|標準の拡張機能を使用します C++ のアラインメント属性は、変数、データ メンバーおよびタグの種類のみに適用。|
|C5031 (レベル 4)|#pragma warning (pop): 別のファイルにプッシュされた警告の状態をポップアップ表示可能性が高い不一致<sup>14.1</sup>|
|C5032 (レベル 4)|#pragma warning (push) ない対応の #pragma warning (pop) が検出された<sup>14.1</sup>|
|C5034|組み込みの使用 '*組み込み*' 関数をにより*関数*ゲスト コードとしてコンパイルする<sup>15.3</sup>|
|C5035|機能を使用して、'*機能*' 関数をにより*関数*ゲスト コードとしてコンパイルする<sup>15.3</sup>|
|C5036 (レベル 1)|/hybrid:x86arm64 でコンパイルするときに、varargs 関数ポインター変換 '*type1*'to'*type2*' <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (レベル 4)|データ メンバー '*member1*'後にデータ メンバー初期化が'*member2*' <sup>15.3</sup>|
|C5039 (レベル 4)|'*関数*':-ehc の extern C 関数に渡されたポインターまたは参照関数をスローする可能性があることにします。 未定義の動作は、この関数が例外をスローした場合に発生する可能性があります。 <sup>15.5</sup>|
|C5042 (レベル 3)|'*関数*': 関数宣言のブロック スコープでは、標準 C++ で指定された 'inline' をすることはできません 'inline' 指定子を削除<sup>15.5。</sup>|
|[C5045](../error-messages/compiler-warnings/c5045.md)|/Qspectre スイッチが指定されている場合、コンパイラはメモリの読み込みに Spectre の軽減策を挿入は<sup>15.7</sup>|

<sup>14.1</sup>この警告は Visual Studio 2015 Update 1 以降を使用します。<br/>
<sup>14.3</sup>この警告は Visual Studio 2015 Update 3 以降を使用します。<br/>
<sup>15.3</sup>この警告は Visual Studio 2017 バージョン 15.3 以降を使用します。<br/>
<sup>15.5</sup>この警告は Visual Studio 2017 バージョン 15.5 以降使用できます。<br/>
<sup>15.7</sup>この警告は Visual Studio 2017 バージョン 15.7 以降使用できます。<br/>
<sup>Perm</sup>しない限り、この警告はオフ、 [/permissive -](../build/reference/permissive-standards-conformance.md)コンパイラ オプションを設定します。<br/>

## <a name="warnings-off-by-default-in-earlier-versions"></a>以前のバージョンで既定でオフの警告

これらの警告は、既定のバージョンの Visual Studio 2015 より前にコンパイラで無効でした。

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (レベル 2)|'*変換*': から切り捨て'*type1*'to'*type2*'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (レベル 1)|'*変数*': ポインター切り捨てから'*型*'to'*型*'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (レベル 1)|'*操作*': から変換'*type1*'to'*type2*' より大きいサイズの|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (レベル 1)|'*演算子*': ゼロ拡張'*type1*'to'*type2*' より大きいサイズの|

この警告は、既定のバージョンの Visual Studio 2012 より前に、のコンパイラではオフになっていました。

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (レベル 4)|型指定子がありません - int と仮定しました。 メモ: C は、現在 int を既定値としてサポートしていません|

## <a name="see-also"></a>関連項目

[warning](../preprocessor/warning.md)