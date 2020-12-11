---
description: 詳細については、ATL プロジェクトでの MFC のサポートに関するページを参照してください。
title: ATL プロジェクトでの MFC のサポート
ms.date: 11/04/2016
f1_keywords:
- vc.atl.addmfc
helpviewer_keywords:
- ATL projects, MFC support
ms.assetid: f90b4276-cb98-4c11-902c-9ebcfe6f954b
ms.openlocfilehash: 8614bfdd5320e0ecdf34cc96251fa8a20f2dede9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157920"
---
# <a name="mfc-support-in-atl-projects"></a>ATL プロジェクトでの MFC のサポート

ATL プロジェクトウィザードで [サポート] [ **mfc** ] を選択した場合、プロジェクトは mfc アプリケーションオブジェクト (クラス) としてアプリケーションを宣言します。 プロジェクトは、MFC ライブラリを初期化し、 [CWinApp](../../mfc/reference/cwinapp-class.md)から派生したクラス (クラス *ProjName*) をインスタンス化します。

このオプションは、属性のない ATL DLL プロジェクトでのみ使用できます。

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

クラスビューでは、アプリケーションオブジェクトクラスとその `InitInstance` 関数と関数を表示でき `ExitInstance` ます。

## <a name="see-also"></a>関連項目

[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)<br/>
[既定の ATL プロジェクト構成](../../atl/reference/default-atl-project-configurations.md)
