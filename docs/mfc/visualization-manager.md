---
description: 詳細については、「視覚化マネージャー」を参照してください。
title: ビジュアル マネージャー
ms.date: 11/19/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: b99331503e4e7e69cc5d8a19fde7641c1b1daeeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143209"
---
# <a name="visualization-manager"></a>ビジュアル マネージャー

ビジュアルマネージャーは、アプリケーション全体の外観を制御するオブジェクトです。 アプリケーションのすべての描画コードを配置できる単一のクラスとして機能します。 MFC ライブラリには、いくつかのビジュアルマネージャーが含まれています。 アプリケーションのカスタムビューを作成する場合は、独自のビジュアルマネージャーを作成することもできます。 次の図は、異なるビジュアルマネージャーが有効になっている場合に同じアプリケーションを示しています。

![CMFCVisualManagerWindows で表示された MyApp](../mfc/media/vmwindows.png "CMFCVisualManagerWindows で表示された MyApp") <br/>
CMFCVisualManagerWindows ビジュアルマネージャーを使用する MyApp

![CMFCVisualManagerVS2005 で表示された MyApp](../mfc/media/vmvs2005.png "CMFCVisualManagerVS2005 で表示された MyApp") <br/>
CMFCVisualManagerVS2005 ビジュアルマネージャーを使用する MyApp

![CMFCVisualManagerOfficeXP で表示された MyApp](../mfc/media/vmofficexp.png "CMFCVisualManagerOfficeXP で表示された MyApp") <br/>
CMFCVisualManagerOfficeXP ビジュアルマネージャーを使用する MyApp

![CMFCVisualManagerOffice2003 で表示された MyApp](../mfc/media/vmoffice2003.png "CMFCVisualManagerOffice2003 で表示された MyApp") <br/>
CMFCVisualManagerOffice2003 ビジュアルマネージャーを使用する MyApp

![CMFCVisualManagerOffice2007 で表示された MyApp](../mfc/media/msoffice2007.png "CMFCVisualManagerOffice2007 で表示された MyApp") <br/>
CMFCVisualManagerOffice2007 ビジュアルマネージャーを使用する MyApp

既定では、ビジュアルマネージャーはいくつかの GUI 要素の描画コードを保持します。 カスタム UI 要素を提供するには、ビジュアルマネージャーの関連描画メソッドをオーバーライドする必要があります。 これらのメソッドの一覧については、「 [Cmfcvisualmanager クラス](../mfc/reference/cmfcvisualmanager-class.md)」を参照してください。 カスタムの外観を提供するためにオーバーライドできるメソッドは、で始まるすべてのメソッドです `OnDraw` 。

アプリケーションは、オブジェクトを1つだけ持つことができ `CMFCVisualManager` ます。 アプリケーションのビジュアルマネージャーへのポインターを取得するには、静的な関数 [Cmfcvisualmanager:: GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance)を呼び出します。 すべてのビジュアルマネージャーはから継承されるため `CMFCVisualManager` 、 `CMFCVisualManager::GetInstance` カスタムビジュアルマネージャーを作成した場合でも、メソッドは適切なビジュアルマネージャーへのポインターを取得します。

カスタムビジュアルマネージャーを作成する場合は、既に存在するビジュアルマネージャーからそれを派生させる必要があります。 から派生する既定のクラスは `CMFCVisualManager` です。 ただし、アプリケーションの場合と同様に、別のビジュアルマネージャーを使用することもできます。 たとえば、ビジュアルマネージャーを使用するが、 `CMFCVisualManagerOffice2007` 区切り記号の表示方法を変更したい場合は、からカスタムクラスを派生させることができ `CMFCVisualManagerOffice2007` ます。 このシナリオでは、区切り記号を描画するメソッドのみを上書きする必要があります。

アプリケーションに特定のビジュアルマネージャーを使用するには、次の2つの方法があります。 1つの方法として、 [Cmfcvisualmanager:: SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) メソッドを呼び出し、適切なビジュアルマネージャーをパラメーターとして渡す方法があります。 次のコード例は、 `CMFCVisualManagerVS2005` このメソッドでビジュアルマネージャーを使用する方法を示しています。

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

アプリケーションでビジュアルマネージャーを使用するもう1つの方法は、手動で作成することです。 アプリケーションは、すべてのレンダリングにこの新しいビジュアルマネージャーを使用します。 ただし、アプリケーションごとにオブジェクトは1つしか存在できないため、 `CMFCVisualManager` 新しいビジュアルマネージャーを作成する前に、現在のビジュアルマネージャーを削除する必要があります。 次の例で `CMyVisualManager` は、は、から派生したカスタムビジュアルマネージャーです `CMFCVisualManager` 。 次のメソッドは、インデックスに応じて、アプリケーションの表示に使用されるビジュアルマネージャーを変更します。

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
        CMFCVisualManager::GetInstance();
        break;

    case CUSTOM_STYLE:
        new CMyVisualManager;
        break;

    default:
        CMFCVisualManager::GetInstance();
        break;
    }

    CMFCVisualManager::GetInstance()->RedrawAll();
}
```

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](../mfc/user-interface-elements-mfc.md)<br/>
[CMFCVisualManager クラス](../mfc/reference/cmfcvisualmanager-class.md)
