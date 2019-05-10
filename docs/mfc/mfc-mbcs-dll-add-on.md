---
title: MFC MBCS DLL アドオン
ms.date: 05/08/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 20145b200a0f8bac8ccb461331d4d233a3b0251e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524815"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL アドオン

MFC のサポートとそのマルチバイト文字セット (MBCS) ライブラリは、Visual Studio 2013 以降で、Visual Studio のインストール中に、追加の手順が必要です。

**Visual Studio 2013**:既定では、Visual Studio 2013 でインストールされている MFC ライブラリは Unicode 開発のみをサポートします。 持つ Visual Studio 2013 の MFC プロジェクトをビルドするには、MBCS の Dll が必要になります、**文字セット**プロパティに設定**マルチ バイト文字セットを使用**または**未設定**します。 ダウンロード時に DLL [Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/download/details.aspx?id=40770)します。

**Visual Studio 2015**: Unicode と MBCS MFC Dll の両方は、Visual C セットアップ コンポーネントに含まれますが、サポートして MFC が既定でインストールされていません。 Visual C++ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、 **［プログラミング言語］** で **［Visual C++］** と **［Microsoft Foundation Classes for C++］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C++ や MFC のインストールを促すプロンプトが表示されます。

**Visual Studio 2017 以降**: Unicode と MBCS MFC Dll がインストールされている、 **C++ によるデスクトップ開発**ワークロードを選択すると**MFC と ATL のサポート**から、**オプション コンポーネント**ウィンドウ。 移動し、インストールにこれらのコンポーネントが含まれていない場合、**ファイル |新しいプロジェクト**ダイアログをクリックして、 **Visual Studio インストーラーを開く**リンク。

## <a name="see-also"></a>関連項目

[MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)
