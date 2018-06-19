---
title: コンパイラの警告 C4600 C4799 から |Microsoft ドキュメント
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4602
- C4603
- C4609
- C4612
- C4613
- C4620
- C4622
- C4629
- C4631
- C4634
- C4635
- C4636
- C4637
- C4638
- C4645
- C4646
- C4655
- C4657
- C4658
- C4662
- C4670
- C4671
- C4672
- C4674
- C4676
- C4678
- C4681
- C4682
- C4685
- C4688
- C4689
- C4690
- C4693
- C4694
- C4695
- C4696
- C4718
- C4719
- C4720
- C4721
- C4722
- C4724
- C4725
- C4728
- C4729
- C4732
- C4739
- C4750
- C4751
- C4752
- C4754
- C4755
- C4757
- C4764
- C4767
- C4770
- C4792
- C4794
dev_langs:
- C++
ms.assetid: 22bd4392-f3be-445c-9f23-6126aebac901
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad29989e89bfe60f2180ee48c411ebd4d3098ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301724"
---
# <a name="compiler-warnings-c4600-through-c4799"></a>コンパイラの警告 C4600 C4799 から

ドキュメントのこのセクションの記事では、コンパイラによって生成される警告メッセージのサブセットについて説明します。

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="warning-messages"></a>警告メッセージ

|警告|メッセージ|
|-------------|-------------|
|[コンパイラの警告 (レベル 1) C4600](../../error-messages/compiler-warnings/compiler-warning-level-1-c4600.md)|#pragma 'macro name': 有効な空でない文字列が必要です|
|コンパイラの警告 (レベル 1) C4602|#pragma pop_macro: 'macro name' この識別子の前の #pragma push_macro がありません|
|コンパイラの警告 (レベル 1) C4603|'*識別子*': マクロが定義されていないか、プリコンパイル済みヘッダーを使用している定義とは異なります|
|コンパイラの警告 (レベル 1) C4604|'*型*': ネイティブおよびマネージの境界を越えて引数を値渡しには、有効なコピー コンス トラクターが必要です。 それ以外の場合、ランタイムの動作は未定義|
|コンパイラの警告 (レベル 1) C4605|'/D*マクロ*' 現在のコマンドラインで指定したが、プリコンパイル済みヘッダーがビルドされたが指定されていません|
|[コンパイラの警告 (レベル 1) C4606](../../error-messages/compiler-warnings/compiler-warning-level-1-c4606.md)|#pragma 警告: '警告番号' が無視されます。コード分析の警告が警告レベルと関連付けられていません。|
|[コンパイラの警告 (レベル 3) C4608](../../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md)|'union_member' は既に初期化子リスト 'union_member' 内の他の共用体メンバーにより初期化されています。|
|コンパイラの警告 (レベル 3、エラー) C4609|'*type1*'既定のインターフェイスから派生した'*インターフェイス*'type' に関する*type2*' です。 別の既定のインターフェイスを使用して '*type1*'、または基本/派生リレーションシップを中断します。|
|[コンパイラの警告 (レベル 4) C4610](../../error-messages/compiler-warnings/compiler-warning-level-4-c4610.md)|'class' のオブジェクトを初期化できません。 - ユーザーに必要なコンス トラクターが定義されています。|
|[コンパイラの警告 (レベル 4) C4611](../../error-messages/compiler-warnings/compiler-warning-level-4-c4611.md)|'function' と C++ オブジェクト デストラクション間の対話は互換性がありません。|
|コンパイラの警告 (レベル 1) C4612|インクルード ファイル名にエラーがあります|
|コンパイラの警告 (レベル 1) C4613|'*シンボル*': セグメントのクラスを変更することはできません|
|[コンパイラの警告 (レベル 1) C4615](../../error-messages/compiler-warnings/compiler-warning-level-1-c4615.md)|#pragma warning: 不明な警告型|
|[コンパイラの警告 (レベル 1) C4616](../../error-messages/compiler-warnings/compiler-warning-level-1-c4616.md)|#pragma warning: 警告番号 'number' 有効なコンパイラ警告ではありません|
|[コンパイラの警告 (レベル 1) C4618](../../error-messages/compiler-warnings/compiler-warning-level-1-c4618.md)|プラグマ パラメーターには、空の文字列が含まれています。プラグマは無視されました|
|[コンパイラの警告 (レベル 3) C4619](../../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md)|#pragma warning: 警告番号 'number' がありません。|
|コンパイラの警告 (レベル 1) C4620|型 'type' に対して後置形式の 'operator ++' は見つかりません。前置形式を使用します|
|[コンパイラの警告 (レベル 1) C4621](../../error-messages/compiler-warnings/compiler-warning-level-1-c4621.md)|'operator--' を型 'type'、前置形式を使用して見つかったありません後置形式|
|コンパイラの警告 (レベル 3) C4622|オブジェクト ファイルでプリコンパイル済みヘッダーの作成中にデバッグ情報を上書きされました: 'file'|
|[コンパイラの警告 (レベル 4) C4623](../../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md)|'derived class': 基底クラスの既定のコンス トラクターがアクセスできないか削除されたために、削除、既定のコンス トラクターは暗黙的に定義|
|[コンパイラの警告 (レベル 1) C4624](../../error-messages/compiler-warnings/compiler-warning-level-1-c4624.md)|'derived class': 基底クラスのデストラクターがアクセスできないか削除されたために、削除、デストラクターは暗黙的に定義|
|[コンパイラの警告 (レベル 4) C4625](../../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md)|'derived class': 基底クラスのコピー コンス トラクターがアクセスできないか削除されたために、削除、コピー コンス トラクターは暗黙的に定義|
|[コンパイラの警告 (レベル 4) C4626](../../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md)|'derived class': 基底クラスの代入演算子がアクセスできないか削除されたために、削除、代入演算子が暗黙的に定義|
|[コンパイラの警告 (レベル 1) C4627](../../error-messages/compiler-warnings/compiler-warning-level-1-c4627.md)|'\<識別子 >': プリコンパイル済みヘッダーの使用を探しているときにスキップ|
|[コンパイラの警告 (レベル 1) C4628](../../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md)|digraphs は -Ze でサポートされていません。 文字のシーケンス 'digraph' は '%s' の代替トークンとして解釈されません。|
|コンパイラの警告 (レベル 4) C4629|digraph が使用されました。文字のシーケンス 'digraph' はトークン 'char' として解釈されます。(これが意図でない場合は、2 文字の間にスペースを挿入してください)|
|[コンパイラの警告 (レベル 1) C4630](../../error-messages/compiler-warnings/compiler-warning-level-1-c4630.md)|'symbol': 'extern' ストレージ クラス指定子のメンバーの定義が無効です|
|コンパイラの警告 (レベル 2) C4631|MSXML または XPath は使用できません。XML ドキュメント コメントは処理されません。 理由|
|[コンパイラの警告 (レベル 1) C4632](../../error-messages/compiler-warnings/compiler-warning-level-1-c4632.md)|XML ドキュメント コメント: ファイルのアクセスが拒否されました: 理由|
|[コンパイラの警告 (レベル 3) C4633](../../error-messages/compiler-warnings/compiler-warning-level-3-c4633.md)|XML ドキュメント コメント ターゲット: エラー: 理由|
|コンパイラの警告 (レベル 4) C4634|XML ドキュメント コメント ターゲット: 適用できません: 理由|
|コンパイラの警告 (レベル 3) C4635|XML ドキュメント コメント対象: XML の形式が正しくありません: 理由|
|コンパイラの警告 (レベル 3) C4636|構築するために適用された XML ドキュメント コメント: タグには、空でない 'attribute' 属性が必要です。|
|コンパイラの警告 (レベル 3 および 4) C4637|XML ドキュメント コメント ターゲット:\<含める > タグは破棄されます。 理由|
|コンパイラの警告 (レベル 3) C4638|XML ドキュメント コメント ターゲット: 不明なシンボル 'symbol' への参照。|
|[コンパイラの警告 (レベル 4) C4639](../../error-messages/compiler-warnings/compiler-warning-level-4-c4639.md)|MSXML エラーの場合は、XML ドキュメント コメントは処理されません。 理由|
|[コンパイラの警告 (レベル 3) C4640](../../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md)|'instance': ローカル スタティック オブジェクトの構築がスレッド セーフではありません。|
|[コンパイラの警告 (レベル 3) C4641](../../error-messages/compiler-warnings/compiler-warning-level-3-c4641.md)|XML ドキュメント コメントには、あいまいな相互参照があります。|
|コンパイラの警告 (レベル 3) C4645|__declspec(noreturn) で宣言された関数に return ステートメントがあります。|
|コンパイラの警告 (レベル 3) C4646|__declspec(noreturn) で宣言された関数に、non-void 戻り値の型があります。|
|コンパイラの警告 (レベル 3) C4647|動作変更: _ _is_pod (*型*) 別の値が、以前のバージョン|
|コンパイラの警告 (レベル 3) C4648|標準属性 'carries_dependency' は無視されます。|
|コンパイラの警告 (レベル 3) C4649|このコンテキストで属性は無視されます。|
|[コンパイラの警告 (レベル 1) C4650](../../error-messages/compiler-warnings/compiler-warning-level-1-c4650.md)|プリコンパイル済みヘッダー以外ではなく、デバッグ情報ヘッダーからのグローバル シンボルのみが使用できます。|
|[コンパイラの警告 (レベル 1) C4651](../../error-messages/compiler-warnings/compiler-warning-level-1-c4651.md)|'定義' プリコンパイル済みヘッダーに定義されていますが、現在のコンパイルではありません。|
|[コンパイラの警告 (レベル 1) C4652](../../error-messages/compiler-warnings/compiler-warning-level-1-c4652.md)|コンパイラ オプション 'option' はプリコンパイル済みヘッダーです。現在のコマンド ライン オプションは、プリコンパイル済みヘッダーで定義されているをよりも優先されます。|
|[コンパイラの警告 (レベル 2) C4653](../../error-messages/compiler-warnings/compiler-warning-level-2-c4653.md)|コンパイラ オプション 'option' はプリコンパイル済みヘッダーです。現在のコマンド ライン オプションが無視されます。|
|コンパイラの警告 (レベル 4) C4654|プリコンパイル済みヘッダーの前に配置されたコードは、行は無視されます。 コードをプリコンパイル済みヘッダーに追加します。|
|コンパイラの警告 (レベル 1) C4655|'symbol': 変数の型が最新のビルドから新規または個所で異なる定義|
|[コンパイラの警告 (レベル 1) C4656](../../error-messages/compiler-warnings/compiler-warning-level-1-c4656.md)|'symbol': データ型の新しいは、最新のビルド以降に変更された、または個所で異なる定義|
|コンパイラの警告 (レベル 1) C4657|式には、最新のビルドから新規データ型が含まれています|
|コンパイラの警告 (レベル 1) C4658|'function': 関数プロトタイプが最新のビルドから新規または別の場所が異なる宣言されています。|
|[コンパイラの警告 (レベル 1) C4659](../../error-messages/compiler-warnings/compiler-warning-level-1-c4659.md)|#pragma 'プラグマ': 予約されたセグメント 'segment' の使用には、動作が定義されていませんが、#pragma comment (linker,...) を使用します。|
|[コンパイラの警告 (レベル 1) C4661](../../error-messages/compiler-warnings/compiler-warning-level-1-c4661.md)|'identifier': 明示的なテンプレート インスタンス化要求に適切な定義がありません。|
|コンパイラの警告 (レベル 1) C4662|明示的なインスタンス化。テンプレート クラス 'identifier1' に 'identifier2' を特定する定義がありません|
|[コンパイラの警告 (レベル 1) C4667](../../error-messages/compiler-warnings/compiler-warning-level-1-c4667.md)|'function': 強制インスタンス化に一致するように定義された関数テンプレートはありません|
|[コンパイラの警告 (レベル 4) C4668](../../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md)|'symbol' が '0' を 'directive' に置換するプリプロセッサ マクロとして定義されていません|
|[コンパイラの警告 (レベル 1) C4669](../../error-messages/compiler-warnings/compiler-warning-level-1-c4669.md)|'cast': 安全でない変換: 'class' はマネージ型のオブジェクト|
|コンパイラの警告 (レベル 4) C4670|'identifier': この基本クラスはアクセスできません|
|コンパイラの警告 (レベル 4) C4671|'identifier': コピー コンス トラクターがアクセス可能ではありません|
|コンパイラの警告 (レベル 4) C4672|'identifier1': あいまいです。 1 つ目を 'identifier2' とします。|
|[コンパイラの警告 (レベル 4) C4673](../../error-messages/compiler-warnings/compiler-warning-level-4-c4673.md)|次の種類 'identifier' がスローされることは考慮されません catch サイト|
|コンパイラの警告 (レベル 1) C4674|'method' は宣言された 'static' であり、パラメーターを 1 つだけ持たなければなりません。|
|コンパイラの警告 (レベル 4) C4676|' % $s ': デストラクターにアクセスできません|
|[コンパイラの警告 (レベル 1) C4677](../../error-messages/compiler-warnings/compiler-warning-level-1-c4677.md)|'function': 公開されたメンバーのシグネチャには、アセンブリ プライベート型 'private_type' が含まれています。|
|コンパイラの警告 (レベル 1) C4678|基底クラス 'base_type' のアクセス可能性が 'derived_type' よりも小さい|
|[コンパイラの警告 (レベル 1) C4679](../../error-messages/compiler-warnings/compiler-warning-level-1-c4679.md)|'member': メンバーをインポートできませんでした|
|[コンパイラの警告 (レベル 4) C4680](../../error-messages/compiler-warnings/compiler-warning-level-4-c4680.md)|'class': コクラスは既定のインターフェイスを指定していません|
|コンパイラの警告 (レベル 4) C4681|'class': コクラスはイベント ソースである既定のインターフェイスを指定していません|
|コンパイラの警告 (レベル 4) C4682|'parameter': 方向性のあるパラメーター属性がいません指定すると、[入力]|
|[コンパイラの警告 (レベル 1) C4683](../../error-messages/compiler-warnings/compiler-warning-level-1-c4683.md)|'function': イベント ソースが 'out' のパラメーターです。複数のイベント ハンドラーをフックするときに注意します。|
|[コンパイラの警告 (レベル 1) C4684](../../error-messages/compiler-warnings/compiler-warning-level-1-c4684.md)|'attribute': 警告!! 属性が原因で、無効なコードの生成: 慎重に使用して|
|コンパイラの警告 (レベル 1) C4685|テンプレート パラメーターの解析中に '> >' が必要ですが、'>>' が見つかりました。|
|[コンパイラの警告 (レベル 3) C4686](../../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md)|'user-defined type': 動作と UDT の戻り値の呼び出し規則に変更がある可能性があります。|
|[コンパイラの警告 (エラー) C4687](../../error-messages/compiler-warnings/compiler-warning-c4687.md)|'class': シールされた抽象クラスはインターフェイス 'interface' を実装できません|
|コンパイラの警告 (レベル 1) C4688|'constraint': 制約リストはアセンブリ プライベート型 'type' を含んでいます|
|コンパイラの警告 (レベル 1) C4689|'%c': #pragma detect_mismatch; 内の文字がサポートされていません#pragma は無視されました|
|コンパイラの警告 (レベル 4) C4690|[ emitidl ( pop ) ]: ポップがプッシュ|
|[コンパイラの警告 (レベル 1) C4691](../../error-messages/compiler-warnings/compiler-warning-level-1-c4691.md)|'type': 参照されていないアセンブリ 'file'、代わりに使用される現在の翻訳単位で定義された型で参照される型が見つかりました|
|[コンパイラの警告 (レベル 1) C4692](../../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md)|'関数': 公開されたメンバーのシグネチャはアセンブリ プライベート ネイティブ型 'native_type' を含んでいます|
|[コンパイラの警告 (レベル 1、エラー) C4693](../../error-messages/compiler-warnings/compiler-warning-c4693.md)|'class': シールされた抽象クラスは任意のインスタンス メンバー 'インスタンス メンバー' できません|
|[コンパイラの警告 (レベル 1、エラー) C4694](../../error-messages/compiler-warnings/compiler-warning-c4694.md)|'class': シールされた抽象クラスは基底クラス 'base_class' を持つことはできません|
|コンパイラの警告 (レベル 1) C4695|#pragma execution_character_set: '文字セット' はサポートされている引数ではありません現在は 'utf-8' がサポートされています|
|コンパイラの警告 (レベル 1) C4696|/ZBvalue1 オプションは範囲です。'value2' と仮定した場合|
|[コンパイラの警告 (レベル 1 およびレベル 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|初期化されていないローカル変数 'name' の使用|
|[コンパイラの警告 (レベル 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)|初期化されていない可能性があるローカル変数 'name' の使用|
|[コンパイラの警告 (レベル 4) C4702](../../error-messages/compiler-warnings/compiler-warning-level-4-c4702.md)|到達できないコード|
|[コンパイラの警告 (レベル 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|初期化されていない可能性があるローカル ポインター変数 '%s' が使用されます。|
|[コンパイラの警告 (レベル 4) C4706](../../error-messages/compiler-warnings/compiler-warning-level-4-c4706.md)|条件式内の割り当て|
|[コンパイラの警告 (レベル 4) C4709](../../error-messages/compiler-warnings/compiler-warning-level-4-c4709.md)|配列インデックスの式内でコンマ演算子|
|[コンパイラの警告 (レベル 4) C4710](../../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md)|'function': インライン関数ではありません。|
|[コンパイラの警告 (レベル 1) C4711](../../error-messages/compiler-warnings/compiler-warning-level-1-c4711.md)|関数 'function' が自動インライン展開を選択しました|
|[コンパイラの警告 (レベル 4) C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md)|関数 'function' がマークされています _ _forceinline としてインライン関数|
|[コンパイラの警告 (レベル 1) C4715](../../error-messages/compiler-warnings/compiler-warning-level-1-c4715.md)|'function': 値を返さないコントロール パスのすべて|
|[コンパイラの警告 (レベル 1、エラー) C4716](../../error-messages/compiler-warnings/compiler-warning-level-1-c4716.md)|'function': 値を返す必要があります|
|[コンパイラの警告 (レベル 1) C4717](../../error-messages/compiler-warnings/compiler-warning-level-1-c4717.md)|'function': すべてのコントロール パスに再帰的で、関数には、ランタイム スタック オーバーフローが発生します|
|コンパイラの警告 (レベル 4) C4718|'function call': 再帰呼び出しには、削除すると、副作用がありません|
|コンパイラの警告 (レベル 1) C4719|Qfast が指定された使用 'f' を 1 つの有効桁数を示すサフィックスとしてするときに、二重の定数|
|コンパイラの警告 (レベル 2) C4720|インライン アセンブラー レポート: 'message'|
|コンパイラの警告 (レベル 1) C4721|'function': 組み込み関数として使用できません。|
|コンパイラの警告 (レベル 1) C4722|'function': デストラクターに値がメモリ リークの可能性|
|[コンパイラの警告 (レベル 3) C4723](../../error-messages/compiler-warnings/compiler-warning-level-3-c4723.md)|0 による除算の潜在的です|
|コンパイラの警告 (レベル 3) C4724|剰余の 2 番目のオペランドは、コンパイル時に 0 と評価され、不定の結果を返します。|
|コンパイラの警告 (レベル 3) C4725|Pentium のモデルによっては、命令が不正確になります。|
|[コンパイラの警告 (レベル 1) C4727](../../error-messages/compiler-warnings/compiler-warning-level-1-c4727.md)|PCH obj_file_1 および obj_file_2 で検出された同じタイムスタンプを持つ pch_file をという名前です。  最初の PCH を使用します。|
|コンパイラの警告 (レベル 1) C4728|/Yl-オプション PCH 参照が必要なために、無視されました|
|コンパイラの警告 (レベル 4) C4729|フロー グラフ ベースの警告の関数が大きすぎます。|
|[コンパイラの警告 (レベル 1) C4730](../../error-messages/compiler-warnings/compiler-warning-level-1-c4730.md)コンパイラの警告 (レベル 1) C4730|'main': _m64 と浮動小数点式が不適切なコードで発生する可能性があります|
|[コンパイラの警告 (レベル 1) C4731](../../error-messages/compiler-warnings/compiler-warning-level-1-c4731.md)|'pointer': フレーム ポインター レジスタ 'register' インライン アセンブラー コードによって変更されました。|
|コンパイラの警告 (レベル 1) C4732|このアーキテクチャでは、組み込みの '% $s' はサポートされていません|
|[コンパイラの警告 (レベル 1) C4733](../../error-messages/compiler-warnings/compiler-warning-level-1-c4733.md)|インライン asm は 'FS:0' に割り当てる: ハンドラーは安全なハンドラーとして登録されていません|
|[コンパイラの警告 (レベル 3) C4738](../../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md)|メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります|
|コンパイラの警告 (レベル 1) C4739|変数 'var' への参照はそのストレージ領域を超えています|
|[コンパイラの警告 (レベル 4) C4740](../../error-messages/compiler-warnings/compiler-warning-level-4-c4740.md)|グローバルな最適化を抑制するまたはインライン asm コードの外部のフロー|
|[コンパイラの警告 (レベル 1) C4742](../../error-messages/compiler-warnings/compiler-warning-level-1-c4742.md)|'var' が 'file1' および 'file2' 内で異なるアラインメント: 番号と番号|
|[コンパイラの警告 (レベル 1) C4743](../../error-messages/compiler-warnings/compiler-warning-level-1-c4743.md)|'type' が 'file1' および 'file2' で別のサイズ: 数とバイト数です。|
|[コンパイラの警告 (レベル 1) C4744](../../error-messages/compiler-warnings/compiler-warning-level-1-c4744.md)|'var' が 'file1' および 'file2' で別の種類: 'type1' および 'type2'|
|[コンパイラの警告 C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md)|揮発性アクセス '*式*' は/volatile:\<iso&#124;ms > 設定; _iso_volatile_load/store 組み込み関数の使用を検討してください|
|[コンパイラの警告 (レベル 1) C4747](../../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md)|呼び出すマネージ 'entrypoint': マネージ コード DLL エントリ ポイントおよび DLL エントリ ポイントから到達した呼び出しを含むローダー ロック下で実行できません|
|コンパイラの警告 (レベル 4) C4749|条件付きでサポートされる: non standard レイアウトの種類に適用される offsetof '*型*'|
|コンパイラの警告 (レベル 1) C4750|'identifier': ループにインライン展開されている _alloca() を含む関数です|
|コンパイラの警告 (レベル 4) C4751|intel (r) ストリーミング SIMD 拡張命令はインライン ASM 内にあるに/arch:AVX は適用されません。|
|コンパイラの警告 (レベル 4) C4752|intel (r) Advanced Vector Extensions; が見つかりません/arch:AVX を使用してください。|
|コンパイラの警告 (レベル 4) C4754|%S (%d) の比較での算術演算の変換規則では、その 1 つの分岐が実行できないを意味します。 '%S' を '%s' (または %d バイトの類似する型) にキャストします。|
|コンパイラの警告 C4755|%S (%d) の比較での算術演算の変換規則では、インライン関数では、その 1 つの分岐を実行できませんを意味します。 '%S' を '%s' (または %d バイトの類似する型) にキャストします。|
|[コンパイラの警告 (レベル 2) C4756](../../error-messages/compiler-warnings/compiler-warning-level-2-c4756.md)|定数演算でオーバーフローしました。|
|コンパイラの警告 (レベル 4) C4757|添字が大きな unsigned の値を負の定数を意図しましたか。|
|コンパイラの警告 (レベル 4) C4764|キャッチ オブジェクトを 16 バイトより大きい値を割り当てることはできません。|
|コンパイラの警告 (レベル 4) C4767|セクション名 '%s' が 8 文字より長いと、リンカーによって切り詰められます|
|コンパイラの警告 (レベル 3) C4768|リンケージ指定する前に _ _declspec 属性は無視されます。|
|コンパイラの警告 C4770|部分的に検証された列挙型 '*名前*' インデックスとして使用|
|コンパイラの警告 C4771|単純なポインターを使用して境界を作成する必要があります。MPX 組み込み関数は無視されます。|
|[コンパイラの警告 (レベル 1、エラー) C4772](../../error-messages/compiler-warnings/compiler-warning-level-1-c4772.md)|#import は存在しない型ライブラリ; から型を参照' missing_type' プレース ホルダーとして使用します。|
|コンパイラの警告 (レベル 4) C4774|'*文字列*': 書式指定文字列の引数で予期されて*数*はない文字列リテラル|
|コンパイラの警告 (レベル 3) C4775|書式指定文字列で使用される標準の拡張機能 '*文字列*'function' の*関数*'|
|コンパイラの警告 (レベル 1) C4776|' %*文字*'関数の書式指定文字列では許可されません'*関数*'|
|コンパイラの警告 (レベル 4) C4777|'*関数*': 書式文字列'*文字列*'型の引数が必要です'*type1*'、可変個引数が、*数*型を持つ '*type2*'|
|コンパイラの警告 (レベル 3) C4778|'*関数*': 書式指定文字列の終端されていない'*文字列*'|
|[コンパイラの警告 (レベル 1) C4788](../../error-messages/compiler-warnings/compiler-warning-level-1-c4788.md)|'identifier': 識別子は 'number' 文字に切り詰められました|
|[コンパイラの警告 (レベル 1) C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|バッファー 'identifier' (サイズが N バイト) でオーバーランが発生します。M バイトがオフセット L から書き込まれます|
|コンパイラの警告 (レベル 2) C4792|関数 '%s' が sysimport を使用して宣言されており、ネイティブ コードから参照されています。リンクに必要なインポート ライブラリ|
|[コンパイラの警告 (レベル 1 および 3) C4793](../../error-messages/compiler-warnings/compiler-warning-level-1-and-3-c4793.md)|'function': ネイティブ: \n\t'reason としてコンパイル関数 '|
|コンパイラの警告 (レベル 1) C4794|スレッド ローカル ストレージ変数 '%s' '%s' から '%s' に変更のセグメント|
|[コンパイラの警告 (レベル 1) C4799](../../error-messages/compiler-warnings/compiler-warning-level-1-c4799.md)|関数 'function' に EMMS 命令がありません。|