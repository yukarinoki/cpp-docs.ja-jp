---
title: '方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用'
ms.custom: get-started-article
ms.date: 07/12/2018
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: ed860a229866991b01266093058b71cc2ae84986
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50669119"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用

Visual Studio 2017 でクラシック Windows デスクトップ プロジェクトを作成するときは、C++ デスクトップ ワークロードがインストールまたは最後に更新されたときにインストールされた Windows 10 SDK のバージョンでビルドする既定で設定には。 このバージョンの Windows SDK は、Windows 7 以降のバージョンと互換性が。 参照してください[Windows ヘッダーを使用して](/windows/desktop/WinProg/using-the-windows-headers)詳細については、特定のバージョンの Windows を対象とします。

SDK の以前のバージョンを対象とする場合は、開く**プロジェクト |プロパティ**し、Windows SDK のバージョンのドロップダウン リストで使用可能なその他の SDK バージョンを選択します。

Visual Studio 2015 と Windows 10 SDK 以降、CRT ライブラリは、1 つ (ucrtbase) ユニバーサル Windows アプリで使用可能である関数を含む、他のすべて (vcruntime140) が含まれている 2 つの部分に分離されました。 Windows 10 SDK には、多数の C99 関数をはじめとする新しい関数が含まれているため、これらの関数を使用するために、次の手順に従う必要があります。 「 [CRT Library Features](../c-runtime-library/crt-library-features.md)」を参照してください。

### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK をターゲットとするには

1. Windows 10 SDK がインストールされていることを確認します。 一部として、Windows 10 SDK がインストールされている、 **C++ によるデスクトップ開発**ワークロード。 スタンドアロン バージョンは、「[のダウンロードと Windows 10 用ツール](https://developer.microsoft.com/windows/downloads)します。

2. プロジェクト ノードのショートカット メニューを開き、 **[Retarget SDK Version] (SDK バージョンの再ターゲット)** をクリックします。

   ![SDK のバージョンを再ターゲット](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")

   **[ソリューション操作の再ターゲット]** ダイアログが表示されます。

   ![ソリューションのアクションを確認して](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

3. **ターゲット プラットフォーム バージョン**ドロップダウン リストで、対象とする Windows 10 SDK のバージョンを選択します。 [OK] ボタンを選択して変更を適用します。

   このコンテキストでは、8.1 が、Windows 8、Windows Server 2012、Windows 7、Windows Server 2008、および Windows Vista との下位互換性も備えた Windows SDK バージョンを参照することに注意してください。

   この手順が成功すると、出力ウィンドウに次のテキストが表示されます。

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

4. プロジェクト プロパティを開いて **[構成プロパティ]、[全般]** セクションで、 **[Windows Target Platform Version] (Windows ターゲット プラットフォームのバージョン)** の値を確認します。 ここで値を変更することは、この手順を実行するのと同じ効果があります。 「 [General Property Page (Project)](../ide/general-property-page-project.md)」を参照してください。

   ![ターゲット プラットフォーム バージョン](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   この操作は、ヘッダー ファイルとライブラリ ファイルへのパスを含むプロジェクトのマクロの値を変更します。 どのような変更を表示する、 **Visual C ディレクトリ**のセクション、**プロジェクトのプロパティ**ダイアログ ボックスなどのプロパティのいずれかの選択、**のインクルード ディレクトリ**を選択ドロップダウン リストを開き、選択\<編集 >。 **[インクルード ディレクトリ]** ダイアログが表示されます。

   ![ディレクトリ ダイアログ ボックスを含める](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   選択、**マクロ >>** ボタン、およびすべての新しい値を表示する Windows SDK マクロのマクロの一覧の下にスクロールします。

   ![Windows SDK マクロ](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

5. この操作を必要に応じて他のプロジェクトでも繰り返し、ソリューションをリビルドします。

### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK をターゲットとするには

1. プロジェクト ノードのショートカット メニューを開き、 **[Retarget SDK Version] (SDK バージョンの再ターゲット)** をクリックします。

2. **ターゲット プラットフォーム バージョン**ドロップダウン リストで、選択**8.1**します。

## <a name="see-also"></a>関連項目

[Windows デスクトップ アプリケーション (Visual C)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)