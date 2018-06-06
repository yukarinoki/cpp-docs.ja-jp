---
title: /DEPENDENTLOADFLAG (既定値依存読み込みフラグを設定します)
description: /DEPENDENTLOADFLAG オプション LoadLibrary を使用して読み込まれた Dll の既定のフラグを設定します。
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dependentloadflag
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a171f3c2edbbbf614a986ff78dd2405e734a1d1
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753711"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (既定値依存読み込みフラグを設定します)

既定負荷フラグのセットが使用されるときに`LoadLibrary`Dll を読み込むために使用します。

## <a name="syntax"></a>構文

> **/DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>引数

|||
|-|-|
*loadflags*|10 進数、先行ゼロ付き 8 進数または 16 進数で、先頭の省略可能な"C"スタイル 16 ビット整数値`0x`、すべてに適用する依存読み込みフラグを指定する[LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)呼び出しです。 既定値は 0 です。

## <a name="remarks"></a>コメント

このオプションは、Visual Studio 2017 の新機能は、Windows 10 RS1 およびそれ以降のバージョンで実行中のアプリにのみ適用されます。 アプリを実行している他のオペレーティング システムでは、このオプションが無視されます。

サポートされるオペレーティング システムでは、このオプションがへの呼び出しを変更した結果`LoadLibrary("dependent.dll")`に相当するのに`LoadLibraryEx("dependent.dll", 0, loadflags)`です。 呼び出す[LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)影響を受けません。 このオプションでは、アプリで読み込まれた Dll に再帰的には適用されません。

このフラグは、DLL の間、植える攻撃を防ぐために使用することができます。 たとえば、アプリで使用`LoadLibrary`依存 DLL を読み込むには、攻撃者で使用される検索パスに同じ名前の DLL を植えますでした`LoadLibrary`など、現在のディレクトリ セーフである DLL の検索モードがある場合、システムのディレクトリの前にするチェック可能性があります無効になります。 セーフの DLL 検索モードでは、検索の順序で後で、ユーザーの現在のディレクトリに配置し、Windows XP SP2 およびそれ以降のバージョンでは既定で有効にします。 詳細については、次を参照してください。[ダイナミック リンク ライブラリの検索順序](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)です。

Link オプションを指定する場合`/DEPENDENTLOADFLAG:0xA00`(結合されたフラグの値`LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`) は、セーフである DLL の検索モードがユーザーのコンピューターで無効な場合でも DLL 検索パスに攻撃者が困難である保護されたディレクトリに制限されます変更します。 使用可能なフラグと、そのシンボリックと numeric 型の値は、次を参照してください。、 *dwFlags*パラメーターの説明を[LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)です。

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で DEPENDENTLOADFLAG リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して**追加オプション**です。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](setting-linker-options.md)
- [リンカー オプション](linker-options.md)
- [DLL を暗黙的にリンクする方法](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [リンク方式を使い分け](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [ダイナミック リンク ライブラリの検索順序](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)
