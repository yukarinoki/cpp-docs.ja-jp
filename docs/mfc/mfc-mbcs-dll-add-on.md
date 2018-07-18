---
title: MFC MBCS DLL アドオン |Microsoft Docs
ms.custom: ''
ms.date: 1/04/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aa6840fe54478b88e201dd09950917b95c7a1cc4
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025735"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL アドオン

MFC のサポートとそのマルチバイト文字セット (MBCS) ライブラリは、Visual Studio 2015 および 2017、Visual Studio 2013 でのインストール中に、追加の手順が必要です。

**Visual Studio 2013**: 既定では、Visual Studio 2013 でインストールされている MFC ライブラリのみをサポートして Unicode 開発します。 持つ Visual Studio 2013 の MFC プロジェクトをビルドするには、MBCS の Dll が必要になります、**文字セット**プロパティに設定**マルチ バイト文字セットを使用**または**未設定**します。 ダウンロード時に DLL [Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/download/details.aspx?id=40770)します。

**Visual Studio 2015**: 両方の Unicode と MBCS MFC Dll、Visual C セットアップ コンポーネントに含まれるが、サポート、MFC が既定でインストールされていません。 Visual C++ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、 **［プログラミング言語］** で **［Visual C++］** と **［Microsoft Foundation Classes for C++］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C++ や MFC のインストールを促すプロンプトが表示されます。

**Visual Studio 2017**: で、Unicode と MBCS MFC Dll がインストールされている、 **C++ によるデスクトップ開発**ワークロードを選択すると**MFC および ATL サポート**から、 **(省略可能)コンポーネント**ウィンドウ。 移動し、インストールにこれらのコンポーネントが含まれていない場合、**ファイル |新しいプロジェクト**ダイアログをクリックして、 **Visual Studio インストーラーを開く**リンク。

## <a name="see-also"></a>関連項目

[MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)

