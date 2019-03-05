---
title: MFC MBCS DLL アドオン
ms.date: 1/04/2018
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 2fdbb5dd862c7d1a8845813c6234fea9e902c1f9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292504"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL アドオン

MFC のサポートとそのマルチバイト文字セット (MBCS) ライブラリは、Visual Studio 2015 および 2017、Visual Studio 2013 でのインストール中に、追加の手順が必要です。

**Visual Studio 2013**:既定では、Visual Studio 2013 でインストールされている MFC ライブラリは Unicode 開発のみをサポートします。 持つ Visual Studio 2013 の MFC プロジェクトをビルドするには、MBCS の Dll が必要になります、**文字セット**プロパティに設定**マルチ バイト文字セットを使用**または**未設定**します。 ダウンロード時に DLL [Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/download/details.aspx?id=40770)します。

**Visual Studio 2015**:Unicode と MBCS MFC Dll の両方は、Visual C セットアップ コンポーネントに含まれますが、サポートして MFC が既定でインストールされていません。 Visual C++ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、 **［プログラミング言語］** で **［Visual C++］** と **［Microsoft Foundation Classes for C++］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C++ や MFC のインストールを促すプロンプトが表示されます。

**Visual Studio 2017**:Unicode と MBCS MFC Dll がインストールされている、 **C++ によるデスクトップ開発**ワークロードを選択すると**MFC と ATL のサポート**から、**オプション コンポーネント**ウィンドウ。 移動し、インストールにこれらのコンポーネントが含まれていない場合、**ファイル |新しいプロジェクト**ダイアログをクリックして、 **Visual Studio インストーラーを開く**リンク。

## <a name="see-also"></a>関連項目

[MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)
