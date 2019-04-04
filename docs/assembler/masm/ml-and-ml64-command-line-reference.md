---
title: ML および ML64 のコマンド ライン リファレンス
ms.date: 08/30/2018
f1_keywords:
- ML
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
ms.openlocfilehash: a452bab03e31436ee5dde476117bce8b73c7571f
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331257"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML および ML64 のコマンド ライン リファレンス

アセンブルし、1 つまたは複数のアセンブリ言語のソース ファイルをリンクします。 コマンド ライン オプションは、大文字小文字を区別します。

Ml64.exe の詳細については、[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)を参照してください。

## <a name="syntax"></a>構文

> ML \[*オプション*] *filename* \[ \[*オプション*] *filename*]
>
> ML64 \[*オプション*] *filename* \[ \[*オプション*] *filename*].\[/link *linkoptions*]

### <a name="parameters"></a>パラメーター

*options*<br/>
次の表に示すオプション。

|オプション|アクション|
|------------|------------|
|**/AT**|小さなメモリ モデルのサポートを有効にします。 .Com のフォーマット ファイルの要件に違反しているコード コンス トラクターは、エラー メッセージを有効にします。 等しくはないことに注意してください、[します。モデル](../../assembler/masm/dot-model.md)**極小**ディレクティブ。<br /><br /> Ml64.exe には使用できません。|
|**/Bl** *ファイル名*|代替のリンカーを選択します。|
|**/c**|のみをアセンブルします。 リンクは行いません。|
|**/coff**|モジュールのオブジェクトの共通のオブジェクト ファイルの形式 (COFF) 型を生成します。 一般に、Win32 アセンブリ言語の開発に必要です。<br /><br /> Ml64.exe には使用できません。|
|**/Cp**|すべてのユーザー識別子の大文字と小文字を保持します。|
|**/Cu**|すべての識別子を大文字に変換 (既定値) にマップします。<br /><br /> Ml64.exe には使用できません。|
|**/Cx**|パブリックおよび extern シンボルの大文字小文字を保持します。|
|**/D** *シンボル*[=*値*]|指定した名前のテキストのマクロを定義します。 場合*値*が不足している場合、これが空白です。 スペースで区切られた複数のトークンは、引用符で囲む必要があります。|
|**/EP**|前処理済みのソースの一覧が (STDOUT に送信) を生成します。 参照してください **/Sf**します。|
|**/ERRORREPORT** [ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** ]|使用することができます ml.exe または ml64.exe は、実行時に失敗した場合、 **/ERRORREPORT**これらの内部エラーに関する情報を Microsoft に送信します。<br /><br /> 詳細については **/ERRORREPORT**を参照してください[/errorReport (内部コンパイラ エラーを報告する)](../../build/reference/errorreport-report-internal-compiler-errors.md)します。|
|**/F** *hexnum*|スタックにサイズを設定*hexnum*バイト (これは、同じ **/リンク/スタック**:*数*)。 値は、16 進表記で表現する必要があります。 間にスペースがある **/F**と*hexnum*します。|
|**/Fe** *ファイル名*|実行可能ファイルを名前します。|
|**/Fl**[*filename*]|アセンブルされたコードを生成します。 参照してください **/Sf**します。|
|**/Fm**[*filename*]|リンカーのマップ ファイルを作成します。|
|**/Fo** *ファイル名*|オブジェクト ファイルの名前を付けます。 詳細については「解説」を参照してください。|
|**/FPi**|浮動小数点演算 (混合言語の場合のみ) のエミュレーターの修正-ups が生成されます。<br /><br /> Ml64.exe には使用できません。|
|**/Fr**[*filename*]|ソース ブラウザーの .sbr ファイルを生成します。|
|**/FR**[*filename*]|ソース ブラウザーの .sbr ファイルの拡張の形式を生成します。|
|**/Gc**|FORTRAN スタイルまたは Pascal 関数を呼び出すと、名前付け規則の使用を指定します。 同じ**オプション言語: PASCAL**します。<br /><br /> Ml64.exe には使用できません。|
|**/Gd**|C スタイルの関数を呼び出すと、名前付け規則の使用を指定します。 同じ**オプション言語: C**します。<br /><br /> Ml64.exe には使用できません。|
|**/GZ**|_ _Stdcall 関数を呼び出すと、名前付け規則の使用を指定します。  同じ**オプション言語: STCALL**します。<br /><br /> Ml64.exe には使用できません。|
|**/H** *数*|外部名を数字の有意文字に制限されます。 既定では 31 文字です。<br /><br /> Ml64.exe には使用できません。|
|**/help**|ML に関するヘルプについては、QuickHelp を呼び出します。|
|**/I** *パス名*|インクルード ファイルのパスを設定します。 最大 10 **/I**オプションを許可します。|
|**/nologo**|成功したアセンブリのメッセージを抑制します。|
|**/omf**|オブジェクトのモジュールのオブジェクトのモジュール ファイル (OMF) の形式の種類を生成します。  **/omf**意味 **/c**;ML.exe が OMF オブジェクトのリンクをサポートしていません。<br /><br /> Ml64.exe には使用できません。|
|**/Sa**|利用可能なすべての情報の一覧をオンにします。|
|**/safeseh**|例外ハンドラーが含まれていないか、またはで宣言されたすべての例外ハンドラーを含む、オブジェクトをマーク[します。SAFESEH](../../assembler/masm/dot-safeseh.md)します。<br /><br /> Ml64.exe には使用できません。|
|**/Sf**|第 1 パスの一覧にリスティング ファイルを追加します。|
|**/Sl** *幅*|1 行の文字数を一覧表示するソースの線の幅を設定します。 範囲は、60 ~ 255 または 0 です。 既定値は 0 です。 同じ[ページ](../../assembler/masm/page.md)幅。|
|**/Sn**|一覧を生成するときに、シンボル テーブルをオフにします。|
|**/Sp** *長さ*|ソース 1 ページあたりの行数でリストのページの長さを設定します。 範囲は、10 ~ 255 または 0 です。 既定値は 0 です。 同じ[ページ](../../assembler/masm/page.md)長さ。|
|**/Ss** *テキスト*|ソースの一覧のテキストを指定します。 同じ[サブタイトル](../../assembler/masm/subtitle.md)テキスト。|
|**/St** *テキスト*|ソースの一覧のタイトルを指定します。 同じ[タイトル](../../assembler/masm/title.md)テキスト。|
|**/Sx**|False の条件の一覧でオンにします。|
|**/Ta** *ファイル名*|ソース ファイルの名前を持つが .asm 拡張機能で終わらないをアセンブルします。|
|**/w**|同じ **/W0/WX**します。|
|**/W** *レベル*|警告レベルの設定場所*レベル*= 0、1、2、または 3 です。|
|**/WX**|警告が生成される場合は、エラー コードを返します。|
|**/X**|INCLUDE 環境変数のパスを無視します。|
|**/Zd**|オブジェクト ファイルには、行番号情報を生成します。|
|**/Zf**|すべてのシンボルをパブリックになります。|
|**/Zi**|オブジェクト ファイルの CodeView 情報が生成されます。|
|**/Zm**|により、**M510** MASM 5.1 の最大の互換性のためのオプション。<br /><br /> Ml64.exe には使用できません。|
|**/Zp**[*配置*]|構造体は、指定したバイトの境界でパックします。 *配置*1、2、または 4 にすることができます。|
|**/Zs**|構文チェックのみを実行します。|
|**/?**|ML コマンドライン構文の概要を表示します。|

*ファイル名*<br/>
ファイルの名前です。

*linkoptions*<br/>
リンク オプションです。  参照してください[リンカー オプション](../../build/reference/linker-options.md)詳細についてはします。

## <a name="remarks"></a>Remarks

ML および ML64 のコマンド ライン オプションは、配置が区別です。 たとえば、ML および ML64 はいくつかで受け入れることができるため、 **/c**オプション、対応する **/Fo**オプションは、前に指定する必要があります **/c**します。 次のコマンドラインの例では、各アセンブリ ファイルの指定のオブジェクト ファイルの仕様を示します。

**ml.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm**

## <a name="environment-variables"></a>環境変数

|変数|説明|
|--------------|-----------------|
|INCLUDE|インクルード ファイルの検索パスを指定します。|
|ML|既定のコマンド ライン オプションを指定します。|
|TMP|一時ファイルのパスを指定します。|

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>
[Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>