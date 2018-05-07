---
title: 'TN016: MFC での C++ の多重継承の使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.inheritance
dev_langs:
- C++
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe1e79324c4c1f7408e1b801cf2be581b9884717
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>テクニカル ノート 16: MFC における C++ の多重継承
ここでは、Microsoft Foundation Classes で複数継承 (MI) を使用する方法について説明します。 多重継承の使用は、MFC で必要はありません。 MI は、すべての MFC クラスでは使用されませんし、クラス ライブラリを作成する必要はありません。  
  
 次のサブトピックでは、MI が使用する一般的な MFC の表現方法と同様の多重継承の制限事項のいくつか取り上げますに与える影響について説明します。 これらの制限の一部は、C++ の一般的な制限です。 MFC アーキテクチャによって他のユーザーが適用されます。  
  
 このテクニカル ノートの最後には、多重継承を使用する完全な MFC アプリケーションを紹介します。  
  
## <a name="cruntimeclass"></a>CRuntimeClass  
 永続性と MFC の使用の動的なオブジェクトの作成のメカニズム、 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md)クラスを一意に識別するデータ構造です。 MFC は、これらの構造体のいずれかが、アプリケーションの各動的やシリアル化可能なクラスに関連付けます。 これらの構造体は、特別な種類の静的オブジェクトを使用して、アプリケーションの起動時に初期化されます`AFX_CLASSINIT`です。  
  
 現在の実装`CRuntimeClass`MI ランタイム型情報をサポートしていません。 これは、ないわけでは、MFC アプリケーションで多重継承を使用することはできません。 ただし、1 つ以上の基本クラスを持つオブジェクトを操作するときに、いくつかの注意があります。  
  
 [使うため](../mfc/reference/cobject-class.md#iskindof)メソッドは正しく型を決定できませんオブジェクトの複数の基底クラスがある場合。 したがって、使用することはできません[CObject](../mfc/reference/cobject-class.md)仮想基底クラス、およびすべての呼び出しとして`CObject`などのメンバー関数[cobject::serialize](../mfc/reference/cobject-class.md#serialize)と[CObject::operator 新しい](../mfc/reference/cobject-class.md#operator_new)その C++ は、適切な関数呼び出しを区別できますので、スコープ修飾子があります。 プログラムでは、MFC 内で多重継承を使用する場合、クラスを格納している、`CObject`基底クラスが基底クラスの一覧で、左端のクラスをする必要があります。  
  
 代わりに使用するが、`dynamic_cast`演算子。 その基本クラスのいずれかに多重継承を持つオブジェクトをキャストすると、関数を使用して、指定された基本クラスのコンパイラは必ずです。 詳細については、次を参照してください。 [dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)です。  
  
## <a name="cobject---the-root-of-all-classes"></a>CObject のすべてのクラスのルート  
 すべての重要なクラスがクラスから直接または間接的に派生`CObject`です。 `CObject` メンバーのデータがありませんが一部の既定の機能です。 多重継承を使用して、2 つ以上から継承は通常する`CObject`-クラスを派生します。 次の例がクラスから継承されるしくみを示しています、 [CFrameWnd](../mfc/reference/cframewnd-class.md)と[CObList](../mfc/reference/coblist-class.md):  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 ここでは`CObject`2 回は含まれています。 つまりへの参照のあいまいさを解消する方法が必要`CObject`メソッドまたは演算子。 `operator new`と[演算子 delete](../mfc/reference/cobject-class.md#operator_delete) 2 つの演算子は、明確にする必要があります。 別の例としては、次のコードは、コンパイル時に、エラーを発生します。  
  
```  
myListWnd.Dump(afxDump);
*// compile time error, CFrameWnd::Dump or CObList::Dump   
```  
  
## <a name="reimplementing-cobject-methods"></a>CObject のメソッドを再実装  
 2 つ以上の新しいクラスを作成する場合が`CObject`、基底クラスを派生する必要があります、`CObject`メソッドを使用するには、他のユーザーをします。 演算子`new`と`delete`は必須と[ダンプ](../mfc/reference/cobject-class.md#dump)をお勧めします。 次の例 reimplements、`new`と`delete`演算子および`Dump`メソッド。  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
 { return CFrameWnd:: operator new(nSize);

}  
    void operator delete(void* p)  
 { CFrameWnd:: operator delete(p);

}  
 
    void Dump(CDumpContent& dc)  
 { CFrameWnd::Dump(dc);

    CObList::Dump(dc);

} 
 ...  
};  
```  
  
## <a name="virtual-inheritance-of-cobject"></a>CObject の仮想継承  
 そのほとんどを継承するように思えます`CObject`関数のあいまいさの問題を解決が、その場合ではありません。 メンバーのデータがないため`CObject`、基底クラス メンバー データの複数のコピーを防ぐために仮想継承する必要はありません。 以前に表示された最初の例では、`Dump`は異なる方法で実装されるため、仮想メソッドがあいまいです。`CFrameWnd`と`CObList`です。 あいまいさを排除する最善の方法では、前のセクションで説明した推奨事項に従います。  
  
## <a name="cobjectiskindof-and-run-time-typing"></a>使うため、実行時の入力  
 MFC でサポートされている、実行時入力メカニズム`CObject`マクロを使用して`DECLARE_DYNAMIC`、 `IMPLEMENT_DYNAMIC`、 `DECLARE_DYNCREATE`、 `IMPLEMENT_DYNCREATE`、`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`です。 これらのマクロは、安全なキャストを保証するために、実行時の型チェックを実行できます。  
  
 これらのマクロは、1 つの基本クラスのみをサポートしは多重継承クラスの限定された方法で動作します。 指定した基本クラス`IMPLEMENT_DYNAMIC`または`IMPLEMENT_SERIAL`初の (または最も左) の基本クラスをする必要があります。 この配置を使用すると、型の左端の基底クラスのみを確認できます。 実行時の型システムを使用して、他の基本クラスはわかりません。 次の例では、実行時のシステムの作業型に対してチェック`CFrameWnd`、に関するが何もないが、`CObList`です。  
  
```  
class CListWnd : public CFrameWnd,
    public CObList  
{  
    DECLARE_DYNAMIC(CListWnd) 
 ...  
};  
IMPLEMENT_DYNAMIC(CListWnd,
    CFrameWnd)  
```  
  
## <a name="cwnd-and-message-maps"></a>CWnd とメッセージ マップ  
 正常に動作するには、MFC メッセージ マップ システムには、次の 2 つの追加要件があります。  
  
-   1 つだけあります`CWnd`-基本クラスを派生します。  
  
-   `CWnd`-派生の基本クラスは、最初 (または最も左) の基本クラスである必要があります。  
  
 動作しなくなりますいくつかの例を次に示します。  
  
```  
class CTwoWindows : public CFrameWnd,
    public CEdit  
 { ... }; *// error : two copies of CWnd  
 
class CListEdit : public CObList,
    public CEdit  
 { ... }; *// error : CEdit (derived from CWnd) must be first  
```  
  
## <a name="a-sample-program-using-mi"></a>多重継承を使用したサンプル プログラム  
 次のサンプルは、1 つから派生クラスで構成されるスタンドアロン アプリケーション`CFrameWnd`と[CWinApp](../mfc/reference/cwinapp-class.md)です。 この方法でアプリケーションを構成するが、これは、1 つのクラスを含む最小の MFC アプリケーションの例はお勧めできません。  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
    // Necessary because of MI disambiguity  
    void* operator new(size_t nSize)  
        { return CFrameWnd::operator new(nSize); }  
    void operator delete(void* p)  
        { CFrameWnd::operator delete(p); }  
  
    // Implementation  
    // CWinApp overrides  
    virtual BOOL InitInstance();  
    // CFrameWnd overrides  
    virtual void PostNcDestroy();  
    afx_msg void OnPaint();  
  
    DECLARE_MESSAGE_MAP()  
  
};  
  
BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)  
    ON_WM_PAINT()  
END_MESSAGE_MAP()  
  
// because the frame window is not allocated on the heap, we must  
// override PostNCDestroy not to delete the frame object  
void CHelloAppAndFrame::PostNcDestroy()  
{  
    // do nothing (do not call base class)  
}  
  
void CHelloAppAndFrame::OnPaint()  
{  
    CPaintDC dc(this);  
    CRect rect;  
    GetClientRect(rect);  
  
    CString s = "Hello, Windows!";  
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);  
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));  
    dc.SetBkMode(TRANSPARENT);  
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);  
}  
  
// Application initialization  
BOOL CHelloAppAndFrame::InitInstance()  
{  
    // first create the main frame  
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",  
        WS_OVERLAPPEDWINDOW, rectDefault))  
        return FALSE;  
  
    // the application object is also a frame window  
    m_pMainWnd = this;            
    ShowWindow(m_nCmdShow);  
    return TRUE;  
}  
  
CHelloAppAndFrame theHelloAppAndFrame;  
```  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

