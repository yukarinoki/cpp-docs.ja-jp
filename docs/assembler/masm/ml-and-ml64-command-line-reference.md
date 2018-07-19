---
title: ML および ML64 のコマンド ライン リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ML
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da3fb143aeaaf6fa8cf31c45b31707fa01bf6898
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057800"
---
# <a name="ml-and-ml64-command-line-reference"></a>ML および ML64 のコマンド ライン リファレンス
アセンブルし、1 つまたは複数のアセンブリ言語のソース ファイルをリンクします。 コマンド ライン オプションは、大文字小文字を区別します。  
  
 Ml64.exe の詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `options`  
 次の表に記載されているオプションです。  
  
|オプション|アクション|  
|------------|------------|  
|**/AT**|小さなメモリ モデルのサポートを有効にします。 .Com 形式のファイルの要件に違反しているコード コンス トラクターのエラー メッセージを有効にします。 等価ではないことに注意してください、[です。モデル](../../assembler/masm/dot-model.md)**極小**ディレクティブです。<br /><br /> Ml64.exe には使用できません。|  
|**/Bl** `filename`|代替リンカーが選択されます。|  
|**/c**|のみをアセンブルします。 リンクされていません。|  
|**/coff**|一般的なオブジェクト ファイル形式 (COFF) の種類のオブジェクト モジュールを生成します。 一般に、Win32 アセンブリ言語の開発に必要です。<br /><br /> Ml64.exe には使用できません。|  
|**/Cp**|すべてのユーザー識別子の大文字と小文字を保持します。|  
|**/Cu**|すべての識別子を大文字に変換する (既定値) にマップします。<br /><br /> Ml64.exe には使用できません。|  
|**/Cx**|公開キーと extern のシンボルの大文字小文字を保持します。|  
|**/D** `symbol`[[=`value`]]|指定した名前のテキストのマクロを定義します。 場合`value`が見つからないかは空白になります。 スペースで区切られた複数のトークンは、引用符で囲む必要があります。|  
|**/EP**|(STDOUT に送信) 前処理されたソースの一覧を生成します。 参照してください **/Sf**です。|  
|**/ERRORREPORT** [ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** ]|使用することができます ml.exe または ml64.exe は、実行時に失敗した場合、 **/ERRORREPORT**これらの内部エラーに関する情報を Microsoft に送信します。<br /><br /> 詳細については **/ERRORREPORT**を参照してください[/errorReport (内部コンパイラ エラーの報告)](../../build/reference/errorreport-report-internal-compiler-errors.md)です。|  
|**/F** `hexnum`|スタックにサイズを設定`hexnum`バイト (これは、同じ**リンク/スタック**:`number`)。 値は、16 進数表記で表現する必要があります。 間にスペースが存在する必要があります **/F**と`hexnum`です。|  
|**/Fe** `filename`|実行可能ファイルの名前を付けます。|  
|**/Fl**[[`filename`]]|アセンブルされたコードを生成します。 参照してください **/Sf**です。|  
|**/Fm**[[`filename`]]|リンカーのマップ ファイルを作成します。|  
|**/Fo** `filename`|オブジェクト ファイルの名前を付けます。 詳細については「解説」セクションを参照してください。|  
|**/FPi**|エミュレーターの fix-up 浮動小数点演算 (混合言語の場合のみ) を生成します。<br /><br /> Ml64.exe には使用できません。|  
|**/Fr**[[`filename`]]|ソース ブラウザー .sbr ファイルを生成します。|  
|**/FR**[[`filename`]]|ソース ブラウザー .sbr ファイルの拡張の形式を生成します。|  
|**/Gc**|FORTRAN または Pascal スタイルの関数を呼び出すと、名前付け規則の使用を指定します。 同じ**オプション言語: PASCAL**です。<br /><br /> Ml64.exe には使用できません。|  
|**/Gd**|C スタイルの関数を呼び出すと、名前付け規則の使用を指定します。 同じ**オプション言語: C**です。<br /><br /> Ml64.exe には使用できません。|  
|**/GZ**|_ _Stdcall 関数を呼び出すと、名前付け規則の使用を指定します。  同じ**オプション言語: STCALL**です。<br /><br /> Ml64.exe には使用できません。|  
|**/H** `number`|外部名を数字の有意文字に制限します。 既定値は、31 文字です。<br /><br /> Ml64.exe には使用できません。|  
|**/help**|ML に関するヘルプについては、クイック ヘルプを呼び出します。|  
|**/I** `pathname`|インクルード ファイルのパスを設定します。 最大 10 個 **/I**オプションを許可します。|  
|**/nologo**|成功したアセンブリのメッセージを抑制します。|  
|**/omf**|オブジェクトのモジュールのオブジェクト モジュールのファイル形式 (OMF) の種類を生成します。  **/omf**意味 **/c**です。ML.exe は OMF オブジェクトのリンクをサポートしていません。<br /><br /> Ml64.exe には使用できません。|  
|**/Sa**|すべての利用可能な情報の一覧をオンにします。|  
|**/safeseh**|例外ハンドラーが含まれていないか、またはで宣言されたすべての例外ハンドラーを含む、オブジェクトをマーク[です。SAFESEH](../../assembler/masm/dot-safeseh.md)です。<br /><br /> Ml64.exe には使用できません。|  
|**/Sf**|初回の一覧にリスティング ファイルを追加します。|  
|**/Sl** `width`|1 行の文字数を一覧表示するソースの線の幅を設定します。 範囲は、60 ~ 255 または 0 です。 既定値は 0 です。 同じ[ページ](../../assembler/masm/page.md)幅。|  
|**/Sn**|一覧を生成するときに、シンボル テーブルをオフにします。|  
|**/Sp** `length`|1 ページあたりの行に一覧表示するソースのページの長さを設定します。 範囲は、10 ~ 255 または 0 です。 既定値は 0 です。 同じ[ページ](../../assembler/masm/page.md)長さ。|  
|**/Ss** `text`|ソース リストのテキストを指定します。 同じ[字幕](../../assembler/masm/subtitle.md)テキスト。|  
|**/St** `text`|ソース リストのタイトルを指定します。 同じ[タイトル](../../assembler/masm/title.md)テキスト。|  
|**/Sx**|False の条件の一覧でオンにします。|  
|**/Ta** `filename`|ソース ファイルの名前が付いていません .asm 拡張機能をアセンブルします。|  
|**/w**|同じ**W0/WX**です。|  
|**/W** `level`|警告レベルを設定、 `level` = 0、1、2、または 3 です。|  
|**/WX**|警告が生成される場合は、エラー コードを返します。|  
|**/X**|INCLUDE 環境パスを無視します。|  
|**/Zd**|オブジェクト ファイル内の行番号情報を生成します。|  
|**/Zf**|すべてのシンボルをパブリックになります。|  
|**/Zi**|オブジェクト ファイルの CodeView 情報が生成されます。|  
|**/Zm**|により、**M510** MASM 5.1 と最大の互換性のためのオプションです。<br /><br /> Ml64.exe には使用できません。|  
|**/Zp**[[`alignment`]]|構造体は、指定したバイトの境界でパックします。 `alignment` 1、2、または 4 にすることができます。|  
|**/Zs**|構文チェックのみを実行します。|  
|**/?**|ML コマンドライン構文の概要を表示します。|  
  
 `filename`  
 ファイルの名前です。  
  
 `linkoptions`  
 リンク オプションです。  参照してください[リンカー オプション](../../build/reference/linker-options.md)詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 ML および ML64 のコマンド ライン オプションは、配置が区別です。 たとえば、ML および ML64 はいくつかで受け入れることができるため **/c**オプションは、対応する、 **/Fo**前にオプションを指定する必要があります **/c**です。 次のコマンドラインの例では、各アセンブリ ファイルの指定のオブジェクト ファイルの仕様を示します。  
  
 **ml.exe /Fo a1.obj /c a.asm /Fo b1.obj /c b.asm**  
  
## <a name="environment-variables"></a>環境変数  
  
|変数|説明|  
|--------------|-----------------|  
|INCLUDE|インクルード ファイルの検索パスを指定します。|  
|ML|既定のコマンド ライン オプションを指定します。|  
|TMP|一時ファイルのパスを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler リファレンス](../../assembler/masm/microsoft-macro-assembler-reference.md)