---
title: MFC MBCS DLL アドオン
ms.date: 1/04/2018
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: a78425ac92aa9ddfe7f0b1b61dde915b3e088383
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558915"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL アドオン

MFC のサポートとそのマルチバイト文字セット (MBCS) ライブラリは、Visual Studio 2015 および 2017、Visual Studio 2013 でのインストール中に、追加の手順が必要です。

**Visual Studio 2013**: 既定では、Visual Studio 2013 でインストールされている MFC ライブラリのみをサポートして Unicode 開発します。 持つ Visual Studio 2013 の MFC プロジェクトをビルドするには、MBCS の Dll が必要になります、**文字セット**プロパティに設定**マルチ バイト文字セットを使用**または**未設定**します。 ダウンロード時に DLL [Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/download/details.aspx?id=40770)します。

**Visual Studio 2015**: 両方の Unicode と MBCS MFC Dll、Visual C セットアップ コンポーネントに含まれるが、サポート、MFC が既定でインストールされていません。 Visual C++ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、 **［プログラミング言語］** で **［Visual C++］** と **［Microsoft Foundation Classes for C++］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C++ や MFC のインストールを促すプロンプトが表示されます。

**Visual Studio 2017**: で、Unicode と MBCS MFC Dll がインストールされている、 **C++ によるデスクトップ開発**ワークロードを選択すると**MFC および ATL サポート**から、 **(省略可能)コンポーネント**ウィンドウ。 移動し、インストールにこれらのコンポーネントが含まれていない場合、**ファイル |新しいプロジェクト**ダイアログをクリックして、 **Visual Studio インストーラーを開く**リンク。

## <a name="see-also"></a>関連項目

[MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)

