---
description: '詳細情報: テクニカルノート 3: オブジェクトへの Windows ハンドルのマッピング'
title: 'テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ'
ms.date: 11/04/2016
f1_keywords:
- vc.mapping
helpviewer_keywords:
- TN003
- handle maps
- Windows handles to objects [MFC]
- mappings [MFC], Windows handles to objects
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
ms.openlocfilehash: e4a0bfa2315ec2b9d67d884d4fdebe314599f454
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216042"
---
# <a name="tn003-mapping-of-windows-handles-to-objects"></a>テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ

このメモでは、Windows オブジェクトハンドルの C++ オブジェクトへのマッピングをサポートする MFC ルーチンについて説明します。

## <a name="the-problem"></a>問題

Windows オブジェクトは、通常、さまざまな [ハンドル](/windows/win32/WinProg/windows-data-types) オブジェクトによって表されます。 MFC クラスは、C++ オブジェクトを使用して windows オブジェクトハンドルをラップします。 MFC クラスライブラリのハンドルラッピング関数を使用すると、特定のハンドルを持つ Windows オブジェクトをラップしている C++ オブジェクトを見つけることができます。 ただし、オブジェクトに C++ ラッパーオブジェクトが含まれておらず、その時点で、システムが C++ ラッパーとして機能する一時オブジェクトを作成する場合もあります。

ハンドルマップを使用する Windows オブジェクトは次のとおりです。

- HWND ([CWnd](../mfc/reference/cwnd-class.md) および `CWnd` -derived クラス)

- HDC ([CDC](../mfc/reference/cdc-class.md) および `CDC` -derived クラス)

- HMENU ([CMenu](../mfc/reference/cmenu-class.md))

- HPEN ([CGdiObject](../mfc/reference/cgdiobject-class.md))

- HBRUSH ( `CGdiObject` )

- HFONT ( `CGdiObject` )

- HBITMAP ( `CGdiObject` )

- HPALETTE ( `CGdiObject` )

- HRGN ( `CGdiObject` )

- HIMAGELIST ([CImageList](../mfc/reference/cimagelist-class.md))

- SOCKET ([CSocket](../mfc/reference/csocket-class.md))

これらのオブジェクトのいずれかのハンドルを指定すると、静的メソッドを呼び出すことによって、ハンドルをラップする MFC オブジェクトを見つけることができ `FromHandle` ます。 たとえば、hwnd *が hwnd の* 場合、次の行は hwnd をラップするへのポインターを返します `CWnd` 。

```
CWnd::FromHandle(hWnd)
```

*Hwnd* に特定のラッパーオブジェクトがない場合は、 `CWnd` *hwnd* をラップするための一時的なが作成されます。 これにより、任意のハンドルから有効な C++ オブジェクトを取得できるようになります。

ラッパーオブジェクトを作成した後は、ラッパークラスのパブリックメンバー変数からハンドルを取得できます。 の場合 `CWnd` 、 *m_hWnd* にはそのオブジェクトの hWnd が含まれます。

## <a name="attaching-handles-to-mfc-objects"></a>アタッチ (ハンドルを MFC オブジェクトに)

新しく作成されたハンドルラッパーオブジェクトと Windows オブジェクトへのハンドルを指定した場合、 `Attach` この例のように関数を呼び出すことによって、2つを関連付けることができます。

```
CWnd myWnd;
myWnd.Attach(hWnd);
```

これにより、 *myWnd* と *hWnd* を関連付けるパーマネントマップにエントリが作成されます。 を呼び出す `CWnd::FromHandle(hWnd)` と、 *myWnd* へのポインターが返されるようになります。 *MyWnd* が削除されると、デストラクターは、Windows の [DestroyWindow](/windows/win32/api/winuser/nf-winuser-destroywindow)関数を呼び出すことによって *hWnd* を自動的に破棄します。 これが望ましくない場合は、 *myWnd* が破棄される前に、 *myWnd* から *hWnd* をデタッチする必要があります (通常、 *myWnd* が定義されているスコープを離れる場合)。 `Detach`メソッドはこれを行います。

```
myWnd.Detach();
```

## <a name="more-about-temporary-objects"></a>一時オブジェクトの詳細

`FromHandle`まだラッパーオブジェクトを持っていないハンドルがに指定されている場合、一時オブジェクトが作成されます。 これらの一時オブジェクトは、ハンドルからデタッチされ、関数によって削除され `DeleteTempMap` ます。 既定では、 [CWinThread:: OnIdle](../mfc/reference/cwinthread-class.md#onidle) は、 `DeleteTempMap` 一時ハンドルマップをサポートする各クラスに対して自動的にを呼び出します。 これは、一時オブジェクトへのポインターが、ポインターが取得された関数からの終了位置を越えて有効であると想定できないことを意味します。

## <a name="wrapper-objects-and-multiple-threads"></a>ラッパーオブジェクトと複数のスレッド

一時オブジェクトとパーマネントオブジェクトは、スレッドごとに保持されます。 つまり、あるスレッドが、一時的か永続的かに関係なく、別のスレッドの C++ ラッパーオブジェクトにアクセスすることはできません。

これらのオブジェクトをあるスレッドから別のスレッドに渡すには、常にネイティブ型として送信し `HANDLE` ます。 あるスレッドから別のスレッドに C++ ラッパーオブジェクトを渡すと、多くの場合、予期しない結果が発生します。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
