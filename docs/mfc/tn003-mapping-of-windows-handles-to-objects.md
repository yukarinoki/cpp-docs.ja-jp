---
title: 'TN003: オブジェクト マッピングの Windows ハンドルと |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mapping
dev_langs:
- C++
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b022c4c42a7373f9bfc23c1fff5be2c1317709de
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692449"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ
この注は、MFC を説明します。 Windows のマッピングをサポートするルーチンが C++ オブジェクトへのハンドルをオブジェクト。  
  
## <a name="the-problem"></a>問題を  
 Windows オブジェクトは、さまざまなによって表される通常[処理](/windows/desktop/WinProg/windows-data-types)MFC クラスのオブジェクトが C++ オブジェクトでの Windows オブジェクト ハンドルをラップします。 MFC クラス ライブラリの関数をラップするハンドルを使用して、特定のハンドルを持つ Windows オブジェクトのラップが C++ オブジェクトを検索できます。 ただし、場合によって、オブジェクトには C++ のラッパー オブジェクトはありません、システム指定の時刻に C++ ラッパーとして機能する一時オブジェクトを作成します。  
  
 ハンドル マップを使用する Windows オブジェクトは次のとおりです。  
  
-   HWND ([CWnd](../mfc/reference/cwnd-class.md)と`CWnd`-派生クラス)  
  
-   HDC ([CDC](../mfc/reference/cdc-class.md)と`CDC`-派生クラス)  
  
-   HMENU ([CMenu](../mfc/reference/cmenu-class.md))  
  
-   HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))  
  
-   HBRUSH (`CGdiObject`)  
  
-   HFONT (`CGdiObject`)  
  
-   HBITMAP (`CGdiObject`)  
  
-   HPALETTE (`CGdiObject`)  
  
-   HRGN (`CGdiObject`)  
  
-   HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))  
  
-   ソケット ([CSocket](../mfc/reference/csocket-class.md))  
  
 ハンドルを指定すると、これらのオブジェクトの 1 つに、静的メソッドを呼び出すことによって、ハンドルをラップする MFC オブジェクトを検索できる`FromHandle`します。 たとえば、HWND と呼ばれる指定された*hWnd*、次の行はへのポインターを返します、`CWnd`をラップする*hWnd*:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 場合*hWnd*が特定のラッパー オブジェクト、一時的な`CWnd`がラップする作成*hWnd*します。 これにより、いずれかのハンドルから有効な C++ オブジェクトを取得します。  
  
 ラッパー オブジェクトを取得したら、ラッパー クラスのパブリック メンバー変数からそのハンドルを取得できます。 場合、 `CWnd`、 *m_hWnd* HWND そのオブジェクトにはが含まれています。  
  
## <a name="attaching-handles-to-mfc-objects"></a>MFC オブジェクトにハンドルをアタッチします。  
 Windows オブジェクトを新しく作成されたハンドル ラッパー オブジェクトおよびハンドルを指定、呼び出すことによって、2 つを関連付けることができます、`Attach`この例のように関数。  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 これは、永続的なマップの関連付けにエントリ*myWnd*と*hWnd*します。 呼び出す`CWnd::FromHandle(hWnd)`へのポインターを返すようになりましたが*myWnd*します。 ときに*myWnd*が削除されると、デストラクターを自動的に破棄*hWnd* 、Windows を呼び出すことによって[DestroyWindow](/windows/desktop/api/winuser/nf-winuser-destroywindow)関数。 これが望ましくない場合*hWnd*からデタッチする必要があります*myWnd*する前に*myWnd*が破棄される (位置のスコープを終了するときに通常*myWnd*が定義されている)。 `Detach`メソッドがこれです。  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>一時オブジェクトの詳細  
 一時オブジェクトが作成されるたびに`FromHandle`ラッパー オブジェクトにまだないハンドルを指定します。 これらの一時オブジェクトは、ハンドルからデタッチされ、によって削除された、`DeleteTempMap`関数。 既定で[CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle)自動的に呼び出します`DeleteTempMap`一時的なハンドルのマップをサポートするクラスごとにします。 つまり、一時オブジェクトへのポインターが有効になります、関数からの終了の時点から、ポインターを取得した場所を想定することはできません。  
  
## <a name="wrapper-objects-and-multiple-threads"></a>オブジェクトのラッパーと複数のスレッド  
 スレッドごとでは、一時的および永続的な両方のオブジェクトが維持されます。 つまり、1 つのスレッドが一時的か永続的かどうかに関係なく、別のスレッドの C++ のラッパー オブジェクトにアクセスできません。  
  
 1 つのスレッド間でこれらのオブジェクトを渡す、常に送信して、ネイティブと`HANDLE`型。 別の 1 つのスレッドから C++ ラッパー オブジェクトを渡すことが予期しない結果が発生する多くの場合。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

