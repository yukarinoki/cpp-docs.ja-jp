---
title: ARM アセンブラーのコマンド ライン リファレンス
ms.date: 08/30/2018
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
ms.openlocfilehash: f49b59a81fbe5f11c0f219d1e1fe83a4ee811c7a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162136"
---
# <a name="arm-assembler-command-line-reference"></a>ARM アセンブラーのコマンド ライン リファレンス

この記事では、Microsoft ARM アセンブラーのコマンド ラインについて*armasm*、共通のオブジェクト ファイル形式 (COFF) の Microsoft による実装に ARMv7 Thumb アセンブリ言語をコンパイルします。 リンカーは、COFF コードと ARM アセンブラーによって、またはオブジェクト ライブラリ、ライブラリアンによって作成されると、C コンパイラによって生成されるオブジェクト コードをリンクできます。

## <a name="syntax"></a>構文

> **armasm** [*options*] *sourcefile* *objectfile*
> **armasm** [*options*] **-o** *objectfile* *sourcefile*

### <a name="parameters"></a>パラメーター

*options*<br/>
次の値を 0 個以上指定できます。

- **-errors** *filename*<br/>
   エラーと警告メッセージをリダイレクト*filename*します。

- **-i** *dir*[**;**<em>dir</em>]<br/>
   インクルード検索パスに指定されたディレクトリを追加します。

- **-predefine***ディレクティブ*<br/>
   シンボルを事前に備える、SETL、セット、またはディレクティブを指定します。<br/>
   例: **armasm.exe-source.asm の「備える 150 数」事前に定義**<br/>
   詳細については、次を参照してください。、 [ARM コンパイラ armasm リファレンス ガイド](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)します。

- **-nowarn**<br/>
   すべての警告メッセージを無効にします。

- **-ignore***警告*<br/>
   指定した警告を無効にします。 使用可能な値は、警告に関するセクションを参照してください。

- **-help**<br/>
   コマンド ライン ヘルプ メッセージを印刷します。

- **-machine** *machine*<br/>
   PE ヘッダーに設定するコンピューターの種類を指定します。  指定できる値*マシン*は。<br/>
   **ARM**— IMAGE_FILE_MACHINE_ARMNT にコンピューターの種類を設定します。 既定値です。<br/>
   **THUMB**— IMAGE_FILE_MACHINE_THUMB にコンピューターの種類を設定します。

- **-oldit**<br/>
   ARMv7 スタイル生成 IT ブロックします。  既定では ARMv8 と互換性のある IT ブロックが生成されます。

- **-via** *filename*<br/>
   追加のコマンドライン引数からの読み取り*filename*します。

- **-16**<br/>
   16 ビット Thumb 命令としてソースをアセンブルします。  既定値です。

- **-32**<br/>
   32 ビット ARM 命令としてソースをアセンブルします。

- **-g**<br/>
   デバッグ情報を生成します。

- **-errorReport:** *option*<br/>
   エラーを Microsoft に報告する方法の内部アセンブラーを指定します。  指定できる値*オプション*は。<br/>
   **none**-レポートを送信しません。<br/>
   **prompt**— 今すぐレポートを送信するように求めます。<br/>
   **queue**-、[次へ] の管理者ログオンでレポートを送信するユーザーに確認します。 既定値です。<br/>
   **send**-レポートを自動的に送信します。

*ソース ファイル*<br/>
ソース ファイルの名前。

*objectfile*<br/>
オブジェクト (出力) ファイルの名前。

## <a name="remarks"></a>Remarks

次の例では、一般的なシナリオで armasm を使用する方法を示します。 まず、armasm を使用して、アセンブリ言語のオブジェクト (.obj) ファイルにソース (.asm) ファイルを作成します。 CL コマンド ライン C コンパイラを使用して、ソース (.c) ファイルをコンパイルし、ARM のオブジェクト ファイルをリンクするリンカー オプションも指定します。

**armasm myasmcode.asm -o myasmcode.obj**

**cl myccode.c /link myasmcode.obj**

## <a name="see-also"></a>関連項目

[ARM アセンブラー診断メッセージ](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
[ARM アセンブラー ディレクティブ](../../assembler/arm/arm-assembler-directives.md)<br/>
