---
title: 'TN003: Windows ハンドルのマップ オブジェクトに |Microsoft ドキュメント'
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
ms.openlocfilehash: bc8658868c36008c5ed6b9db9747eb63ae37e4d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382974"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ
この注の説明、MFC Windows をマップをサポートするルーチンが C++ オブジェクトへのハンドルをオブジェクトします。  
  
## <a name="the-problem"></a>問題を  
 Windows のオブジェクトは、さまざまなによって表される通常[処理](http://msdn.microsoft.com/library/windows/desktop/aa383751)MFC クラスのオブジェクトが C++ オブジェクトでの Windows オブジェクト ハンドルをラップします。 MFC クラス ライブラリの関数をラップするハンドルを使用して、C++ オブジェクトはラップして、特定のハンドルを持っている Windows のオブジェクトを検索できます。 ただし、オブジェクトでは、C++ のラッパー オブジェクトがない場合がありますして、指定の時刻に C++ のラッパーとして機能する一時オブジェクトが作成されます。  
  
 ハンドルのマップを使用する Windows のオブジェクトは次のとおりです。  
  
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
  
 ハンドルを指定すると、これらのオブジェクトのいずれにも、静的メソッドを呼び出すことによって、ハンドルをラップする MFC オブジェクトを見つけることができます`FromHandle`です。 たとえばと呼ばれる HWND をその`hWnd`、次の行はへのポインターを返します、`CWnd`をラップする`hWnd`:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 場合`hWnd`が特定のラッパー オブジェクト、一時的な`CWnd`をラップする作成`hWnd`です。 これにより、いずれかのハンドルから有効な C++ オブジェクトを取得します。  
  
 ラッパー オブジェクトを作成したら、ラッパー クラスのパブリック メンバー変数からのハンドルを取得できます。 場合、 `CWnd`、 `m_hWnd` HWND そのオブジェクトにはが含まれています。  
  
## <a name="attaching-handles-to-mfc-objects"></a>MFC オブジェクトにハンドルをアタッチします。  
 Windows のオブジェクトを新しく作成されたハンドルのラッパー オブジェクトおよびハンドルを指定、呼び出すことによって、2 つを関連付けることができます、`Attach`例のように関数。  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);
```  
  
 これはパーマネント マップの関連付けにエントリ`myWnd`と`hWnd`です。 呼び出す`CWnd::FromHandle(hWnd)`はへのポインターを返します`myWnd`です。 ときに`myWnd`が削除されると、デストラクターを自動的に破棄`hWnd`、Windows を呼び出すことによって[DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682)関数。 これが必要ない場合`hWnd`からデタッチする必要があります`myWnd`する前に`myWnd`が破棄される (これでスコープを終了するときに通常`myWnd`定義されました)。 `Detach`メソッドではこのです。  
  
```  
myWnd.Detach();
```  
  
## <a name="more-about-temporary-objects"></a>一時オブジェクトの詳細  
 一時オブジェクトが作成されるたびに`FromHandle`ラッパー オブジェクトにまだないハンドルを指定します。 これらの一時オブジェクトは、ハンドルからデタッチされ、によって削除された、`DeleteTempMap`関数。 既定では[CWinThread::OnIdle](../mfc/reference/cwinthread-class.md#onidle)を自動的に呼び出して`DeleteTempMap`一時ハンドルのマップをサポートするクラスごとにします。 つまり、一時的なオブジェクトへのポインターが有効になります、関数からの終了の時点、ポインターを取得したを想定することはできません。  
  
## <a name="wrapper-objects-and-multiple-threads"></a>ラッパー オブジェクトと複数のスレッド  
 スレッド単位では、一時的と永続的の両方のオブジェクトが維持されます。 つまり、1 つのスレッドが一時的か永続的かどうかに関係なく、別のスレッドの C++ のラッパー オブジェクトにアクセスできません。  
  
 これらのオブジェクトを別の 1 つのスレッドに渡す、常に送信して、ネイティブと`HANDLE`型です。 1 つのスレッドから C++ のラッパー オブジェクトを渡す多くの場合、予期しない結果。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

