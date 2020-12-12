---
description: 詳細については、「アプリケーションの設定」、「MFC DLL ウィザード」を参照してください。
title: '[アプリケーションの設定] (MFC DLL ウィザード)'
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: da9579ef9a834fa0c2362b1569c2efa808132faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322799"
---
# <a name="application-settings-mfc-dll-wizard"></a>[アプリケーションの設定] (MFC DLL ウィザード)

MFC DLL ウィザードのこのページを使用すると、基本的な機能をデザインし、新しい MFC DLL プロジェクトに追加できます。

## <a name="dll-type"></a>[DLL の種類]

作成する DLL の種類を選択します。

- **共有 MFC dll を使用するレギュラー MFC DLL**

   MFC ライブラリを共有 DLL としてプログラムにリンクするには、このオプションを選択します。 このオプションを使用すると、DLL と呼び出し元のアプリケーションの間で MFC オブジェクトを共有することはできません。 プログラムによって、実行時に MFC ライブラリへの呼び出しが行われます。 このオプションを選択すると、MFC ライブラリを使用する複数の実行ファイルで構成されている場合、プログラムのディスクとメモリの要件が軽減されます。 Win32 と MFC の両方のプログラムで、DLL 内の関数を呼び出すことができます。 この種類のプロジェクトで MFC DLL を再配布する必要があります。

- **MFC が静的にリンクされたレギュラー MFC DLL**

   ビルド時にプログラムを MFC ライブラリに静的にリンクする場合は、このオプションを選択します。 Win32 と MFC の両方のプログラムで、DLL 内の関数を呼び出すことができます。 このオプションを使用すると、プログラムのサイズが大きくなりますが、この種類のプロジェクトで MFC DLL を再配布する必要はありません。 DLL と呼び出し元のアプリケーションの間で MFC オブジェクトを共有することはできません。

- **MFC 拡張 DLL**

   このオプションは、プログラムで実行時に MFC ライブラリを呼び出す必要がある場合や、DLL と呼び出し元アプリケーションの間で MFC オブジェクトを共有する場合に選択します。 このオプションを使用すると、プログラムが MFC ライブラリを使用する複数の実行可能ファイルで構成されている場合に、ディスクとメモリの要件が軽減されます。 DLL 内の関数を呼び出すことができるのは、MFC プログラムだけです。 この種類のプロジェクトで MFC DLL を再配布する必要があります。

## <a name="additional-features"></a>その他の機能

MFC DLL がオートメーションをサポートする必要があるかどうか、および Windows ソケットをサポートする必要があるかどうかを選択します。

- **Automation**

   別のプログラムで実装されているオブジェクトをプログラムで操作できるようにするには、[ **オートメーション** ] を選択します。 **オートメーション** を選択すると、プログラムも他のオートメーションクライアントに公開されます。 詳細については、「 [Automation](../../mfc/automation.md) 」を参照してください。

- **Windows ソケット**

   プログラムが Windows ソケットをサポートしていることを示すには、このオプションを選択します。 Windows sockets を使用すると、TCP/IP ネットワーク経由で通信するプログラムを作成できます。

   Windows ソケットサポートを含む MFC DLL が作成されると、 [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) はソケットのサポートを初期化し、mfc ヘッダーファイル stdafx.h には AfxSock が含まれます。

## <a name="see-also"></a>関連項目

[MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)<br/>
[MFC DLL プロジェクトの作成](../../mfc/reference/creating-an-mfc-dll-project.md)
