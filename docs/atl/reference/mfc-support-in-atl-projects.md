---
title: ATL プロジェクトで MFC のサポート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.addmfc
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad9e55fa296b8a39e4c77ab33240c837b6c871ea
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063498"
---
# <a name="mfc-support-in-atl-projects"></a>ATL プロジェクトで MFC サポート

選択した場合**サポート MFC** ATL プロジェクト ウィザードで、プロジェクトは、MFC アプリケーション オブジェクト (クラス) としてアプリケーションを宣言します。 プロジェクトが MFC ライブラリを初期化し、クラスをインスタンス化します (クラス*ProjName*) から派生する[CWinApp](../../mfc/reference/cwinapp-class.md)します。

このオプションは、属性なし ATL DLL プロジェクトにのみ使用できます。

```
class CProjNameApp : public CWinApp
{
public:

// Overrides
    virtual BOOL InitInstance();
virtual int ExitInstance();
DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CProjNameApp, CWinApp)
END_MESSAGE_MAP()

CProjNameApp theApp;

BOOL CProjNameApp::InitInstance()
{
    return CWinApp::InitInstance();

}

int CProjNameApp::ExitInstance()
{
    return CWinApp::ExitInstance();

}
```

アプリケーションのオブジェクト クラスを表示することができ、その`InitInstance`と`ExitInstance`クラス ビュー内の関数。

## <a name="see-also"></a>関連項目

[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)<br/>
[ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

