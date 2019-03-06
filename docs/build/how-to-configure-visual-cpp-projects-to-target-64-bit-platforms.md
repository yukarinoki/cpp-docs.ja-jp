---
title: '方法: Visual C プロジェクトを 64 ビット、x64 を構成プラットフォーム'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: 17255a5671880063f030ed0087c1fa839c5a14ef
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421376"
---
# <a name="how-to-configure-visual-c-projects-to-target-64-bit-x64-platforms"></a>方法: Visual C プロジェクトを 64 ビット、x64 を構成プラットフォーム

Visual Studio IDE でプロジェクト構成を使用すると、プラットフォームに C++ アプリケーションを 64 ビット、x64 を設定します。 Win32 プロジェクトの設定を 64 ビットのプロジェクト構成に移行することもできます。

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>64 ビットのプラットフォームを対象とするように C++ アプリケーションを設定するには

1. 構成する C++ プロジェクトを開きます。

1. そのプロジェクトのプロパティ ページが開きます。 詳細については、「[プロジェクト プロパティの操作](../ide/working-with-project-properties.md)」を参照してください。

   > [!NOTE]
   > .NET プロジェクトでは、必ず、**構成プロパティ**ノード、またはその子ノードのいずれかで選択されて、 **\<プロジェクト名 > プロパティ ページ** ダイアログ ボックスそれ以外、 。**Configuration Manager**ボタンは使用できません。

1. **[構成マネージャー]** ボタンを選択して **[構成マネージャー]** ダイアログ ボックスを開きます。

1. **アクティブ ソリューション プラットフォーム**ドロップダウン リストで、 **\<新規作成 >** を開くオプション、**新しいソリューション プラットフォーム** ダイアログ ボックス。

1. **入力または選択、新しいプラットフォーム**ドロップダウン リスト、ターゲット プラットフォームの 64 ビットを選択します。

   > [!NOTE]
   > **[新しいソリューション プラットフォーム]** ダイアログ ボックスで、 **[設定のコピー元]** オプションを使用して、既存のプロジェクト設定を新しい 64 ビットのプロジェクト構成にコピーします。

1. **[OK]** を選択します。 前の手順で選択したプラットフォームが **[構成マネージャー]** ダイアログ ボックスの **[アクティブ ソリューション プラットフォーム]** の下に表示されます。

1. 選択、**閉じる**ボタン、 **Configuration Manager**  ダイアログ ボックスを選び、 **OK**ボタン、  **\<Projectname >プロパティ ページ** ダイアログ ボックス。

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Win32 プロジェクトの設定を 64 ビットのプロジェクト構成に移行するには

- 64 ビットのプラットフォームを対象とするプロジェクトの設定中に **[新しいソリューション プラットフォーム]** ダイアログ ボックスが開いたら、 **[設定のコピー元]** ドロップダウン リストで **[Win32]** を選択します。 これらのプロジェクト設定は、プロジェクト レベルで自動的に更新されます。

  - [/MACHINE](../build/reference/machine-specify-target-platform.md) リンカー オプションは **/MACHINE:X64**に設定されます。

  - **[出力の登録]** はオフにされます。 詳細については、「 [Linker Property Pages](../ide/linker-property-pages.md)」を参照してください。

  - **[ターゲット環境]** は **/env x64**に設定されます。 詳細については、次を参照してください。 [MIDL プロパティ ページ。一般的な](../ide/midl-property-pages-general.md)します。

  - **[パラメーターの確認]** はクリアされ、既定値にリセットされます。 詳細については、次を参照してください。 [MIDL プロパティ ページ。高度な](../ide/midl-property-pages-advanced.md)します。

  - **[デバッグ情報の形式]** が Win32 プロジェクト構成で **/ZI** に設定された場合、64 ビットのプロジェクト構成では **/Zi** に設定されます。 詳細については、「[/Z7、/Zi、/ZI (デバッグ情報の形式)](../build/reference/z7-zi-zi-debug-information-format.md)」を参照してください。

  > [!NOTE]
  > プロジェクトのプロパティは、ファイル レベルでオーバーライドされる場合、いずれも変更されません。

## <a name="see-also"></a>関連項目

[.NET framework の 64 ビット アプリケーション](/dotnet/framework/64-bit-apps)<br/>
[64 ビット、x64 ターゲット用の Visual C の構成](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
[64 ビット アプリケーションをデバッグする](/visualstudio/debugger/debug-64-bit-applications)
