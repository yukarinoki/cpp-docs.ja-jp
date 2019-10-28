---
title: '方法: Windows デスクトップアプリケーションでの Windows 10 SDK の使用'
ms.custom: get-started-article
ms.date: 07/12/2018
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: 8dbf18d24c0369507743c3c1da624838f9ab4703
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "69513828"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>方法: Windows デスクトップアプリケーションでの Windows 10 SDK の使用

Visual Studio 2017 でクラシック Windows デスクトッププロジェクトを作成すると、既定では、デスクトップワークロードのC++インストール時または最終更新時にインストールされたバージョンの WINDOWS 10 SDK を使用してビルドするように設定されます。 このバージョンの Windows SDK は、Windows 7 以降と互換性があります。 特定のバージョンの Windows を対象とする方法の詳細について[は、「Windows ヘッダーの使用](/windows/win32/WinProg/using-the-windows-headers)」を参照してください。

以前のバージョンの SDK を対象とする場合は、Project | を開くことができます。 **[プロパティ**] をクリックし、[Windows SDK のバージョン] ボックスの一覧で使用可能な他の SDK のバージョンを選択します。

Visual Studio 2015 と Windows 10 SDK 以降では、CRT ライブラリは2つの部分に分けられていました。1つはユニバーサル Windows アプリで使用可能な関数を含む 1 (ucrtbase) で、もう1つは他のすべてを含む (vcruntime140) です。 Windows 10 SDK には、多数の C99 関数をはじめとする新しい関数が含まれているため、これらの関数を使用するために、次の手順に従う必要があります。 「 [CRT Library Features](../c-runtime-library/crt-library-features.md)」を参照してください。

### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK をターゲットとするには

1. Windows 10 SDK がインストールされていることを確認します。 Windows 10 SDK は、ワークロード**を使用C++したデスクトップ開発**の一部としてインストールされます。 スタンドアロンバージョンについては、「 [Windows 10 用のダウンロードとツール](https://developer.microsoft.com/windows/downloads)」を参照してください。

2. プロジェクト ノードのショートカット メニューを開き、 **[Retarget SDK Version] (SDK バージョンの再ターゲット)** をクリックします。

   ![SDK バージョン の再ターゲット](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")

   **[ソリューション操作の再ターゲット]** ダイアログが表示されます。

   ![ソリューションアクションの確認](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

3. **[ターゲットプラットフォームのバージョン]** ドロップダウンリストで、対象とする WINDOWS 10 SDK のバージョンを選択します。 [OK] ボタンを選択して変更を適用します。

   このコンテキストでは、8.1 が、Windows 8、Windows Server 2012、Windows 7、Windows Server 2008、および Windows Vista との下位互換性も備えた Windows SDK バージョンを参照することに注意してください。

   この手順が成功すると、出力ウィンドウに次のテキストが表示されます。

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

4. プロジェクト プロパティを開いて **[構成プロパティ]、[全般]** セクションで、 **[Windows Target Platform Version] (Windows ターゲット プラットフォームのバージョン)** の値を確認します。 ここで値を変更することは、この手順を実行するのと同じ効果があります。 「 [General Property Page (Project)](../build/reference/general-property-page-project.md)」を参照してください。

   ![ターゲットプラットフォームのバージョン](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   この操作は、ヘッダー ファイルとライブラリ ファイルへのパスを含むプロジェクトのマクロの値を変更します。 変更内容を確認するには、 **[プロジェクトのプロパティ]** ダイアログボックスの **[ビジュアルC++ディレクトリ]** セクションで、 **[インクルードディレクトリ]** などのプロパティの1つを選択し\<、ドロップダウンリストを開き、[> の編集] を選択します。 **[インクルード ディレクトリ]** ダイアログが表示されます。

   ![[ディレクトリを含める] ダイアログボックス](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   **[マクロ > >]** ボタンをクリックし、マクロの一覧を Windows SDK マクロにスクロールして、すべての新しい値を表示します。

   ![Windows SDK マクロ](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

5. この操作を必要に応じて他のプロジェクトでも繰り返し、ソリューションをリビルドします。

### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK をターゲットとするには

1. プロジェクト ノードのショートカット メニューを開き、 **[Retarget SDK Version] (SDK バージョンの再ターゲット)** をクリックします。

2. **[ターゲットプラットフォームバージョン]** ドロップダウンリストで、 **[8.1]** を選択します。

## <a name="see-also"></a>関連項目

[Windows デスクトップアプリケーション (ビジュアルC++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)