---
title: '方法: Windows 10 を使用して、Windows デスクトップ アプリケーションで SDK |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 04/19/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2dae6f31082176c94cdf12cf0cdb42ba13aa93fe
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用
Visual Studio 2017 でクラシック Windows デスクトップ プロジェクトを作成する場合は設定して既定では、C++ デスクトップ ワークロードがインストールまたは最後に更新されたときにインストールされている Windows 10 SDK のバージョンでビルドします。 このバージョンの Windows SDK は、最近のすべての Windows リリースと互換性が。 SDK の以前のバージョンを対象とする場合は、プロジェクトを開くことができます |プロパティの Windows SDK のバージョンのドロップダウン内で使用可能なその他の SDK バージョンを選択します。  
  
 Visual Studio 2015 および Windows 10 SDK 以降、CRT ライブラリが、1 つ (ucrtbase) をユニバーサル Windows アプリで使用する使用可能な関数を含む、他のすべて (vcruntime140) が含まれる 2 つの部分に分けられます。 Windows 10 SDK には、多数の C99 関数をはじめとする新しい関数が含まれているため、これらの関数を使用するために、次の手順に従う必要があります。 「[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。  
  
### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK をターゲットとするには  
  
1.  Windows 10 SDK がインストールされていることを確認します。 一部として、Windows 10 SDK がインストールされている、 **C++ を使用したデスクトップ開発**ワークロード。 スタンドアロン バージョンは、「[ダウンロードおよび Windows 10 用ツール](https://developer.microsoft.com/windows/downloads)です。

  
2.  プロジェクト ノードのショートカット メニューを開き、 **[Retarget SDK Version] (SDK バージョンの再ターゲット)** をクリックします。  
  
     ![SDK のバージョンを再ターゲット](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")  
  
     **[ソリューション操作の再ターゲット]** ダイアログが表示されます。  
  
     ![ソリューションの操作を確認](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")  
  
3.  **ターゲット プラットフォーム バージョン** ドロップダウン リストで、対象となる Windows 10 SDK のバージョンを選択します。 [OK] ボタンを選択して変更を適用します。  
  
     このコンテキストでは、8.1 が、Windows 8、Windows Server 2012、Windows 7、Windows Server 2008、および Windows Vista との下位互換性も備えた Windows SDK バージョンを参照することに注意してください。  
  
     この手順が成功すると、出力ウィンドウに次のテキストが表示されます。  
  
     `Retargeting End: 1 completed, 0 failed, 0 skipped`  
  
4.  プロジェクト プロパティを開いて **[構成プロパティ]、[全般]** セクションで、 **[Windows Target Platform Version] (Windows ターゲット プラットフォームのバージョン)** の値を確認します。 ここで値を変更することは、この手順を実行するのと同じ効果があります。 「 [General Property Page (Project)](../ide/general-property-page-project.md)」を参照してください。  
  
     ![ターゲット プラットフォーム バージョン](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")  
  
     この操作は、ヘッダー ファイルとライブラリ ファイルへのパスを含むプロジェクトのマクロの値を変更します。 プロジェクトのプロパティ ダイアログ ボックスの Visual C ディレクトリ セクションで、変更内容を表示するインクルード ディレクトリ などプロパティのいずれかの場合は選択して、ドロップダウン リストを開き、選択\<編集 >。 **[インクルード ディレクトリ]** ダイアログが表示されます。  
  
     ![インクルード ディレクトリ](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")  
  
     選択、**マクロ >>**  ボタン、およびすべての新しい値を表示する Windows SDK マクロにマクロの一覧を下にスクロールします。  
  
     ![Windows SDK マクロ](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")  
  
5.  この操作を必要に応じて他のプロジェクトでも繰り返し、ソリューションをリビルドします。  
  
### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK をターゲットとするには  
  
1.  プロジェクト ノードのショートカット メニューを開き、 **[Retarget SDK Version] (SDK バージョンの再ターゲット)** をクリックします。  
  
2.  [ターゲット プラットフォーム バージョン] ドロップダウン リストで、8.1 を選択します。  
  
## <a name="see-also"></a>関連項目  
 [Windows デスクトップ アプリケーション (Visual C)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)
