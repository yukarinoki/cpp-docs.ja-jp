---
title: アプリケーションの設定、MFC DLL ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a243b790881452a983c43fb92d8ebea18c26bcc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="application-settings-mfc-dll-wizard"></a>[アプリケーションの設定] \(MFC DLL ウィザード)
MFC DLL ウィザードのこのページを使用して、設計して新しい MFC DLL プロジェクトに基本的な機能を追加します。  
  
## <a name="dll-type"></a>[DLL の種類]  
 作成する DLL の種類を選択します。  
  
 **使用して標準の MFC DLL が MFC DLL を共有**  
 MFC ライブラリを共有 DLL として、プログラムにリンクするには、このオプションを選択します。 このオプションを使用すると、DLL と呼び出し元のアプリケーション間で MFC オブジェクトを共有できません。 プログラムは、実行時に、MFC ライブラリへの呼び出しがします。 このオプションは、MFC ライブラリを使用する複数の実行ファイルで構成される場合に、プログラムのディスクとメモリの量を削減します。 Win32 と MFC の両方のプログラムは、DLL の関数を呼び出すことができます。 この種類のプロジェクトでは MFC DLL を再配布する必要があります。  
  
 **MFC での正規の MFC DLL が静的にリンク**  
 MFC ライブラリをビルド時にプログラムを静的にリンクするには、このオプションを選択します。 Win32 と MFC の両方のプログラムは、DLL の関数を呼び出すことができます。 このオプションでは、プログラムのサイズが増えますが、中に、この種類のプロジェクトでは MFC DLL を再配布する必要はありません。 MFC オブジェクトは、DLL と呼び出し元のアプリケーション間で共有できません。  
  
 **MFC 拡張 DLL**  
 場合は、プログラム実行時に、MFC ライブラリへの呼び出しを作成して、DLL と呼び出し元のアプリケーション間で MFC オブジェクトを共有する場合は、このオプションを選択します。 このオプションは、MFC ライブラリを使用する複数の実行可能ファイルで構成される場合に、プログラムのディスクとメモリの量を削減します。 MFC プログラムだけでは、DLL の関数を呼び出すことができます。 この種類のプロジェクトでは MFC DLL を再配布する必要があります。  
  
## <a name="additional-features"></a>その他の機能  
 Windows ソケットをサポートするかどうかと、MFC DLL がオートメーションをサポートするかどうかを選択します。  
  
 **オートメーション**  
 選択**オートメーション**プログラムの別のプログラムに実装されているオブジェクトの操作に許可します。 選択すると**オートメーション**も他のオートメーション クライアントにプログラムを公開します。 参照してください[オートメーション](../../mfc/automation.md)詳細についてはします。  
  
 **Windows ソケット**  
 プログラムが Windows ソケットをサポートしていることを示すためにこのオプションを選択します。 Windows ソケットを使用すると、TCP/IP ネットワーク経由で通信するプログラムを作成できます。  
  
 Windows で、MFC DLL のソケットのサポートが作成、[場合は](../../mfc/reference/cwinapp-class.md#initinstance)ソケットの初期化をサポートし、MFC ヘッダー ファイル StdAfx.h AfxSock.h が含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL プロジェクトの作成](../../mfc/reference/creating-an-mfc-dll-project.md)

