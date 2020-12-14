---
description: '詳細については、次を参照してください: テクニカルノート 16: C++ を使用した MFC での多重継承'
title: 'テクニカル ノート 16: MFC における C++ の多重継承'
ms.date: 06/28/2018
f1_keywords:
- vc.inheritance
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
ms.openlocfilehash: ac4b082a5dc33e93098453714acd25fbd0c18438
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215951"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>テクニカル ノート 16: MFC における C++ の多重継承

このメモでは、Microsoft Foundation Classes で多重継承 (MI) を使用する方法について説明します。 MFC では、MI を使用する必要はありません。 MI は、MFC クラスでは使用されず、クラスライブラリの記述には必要ありません。

次のサブトピックでは、MI が一般的な MFC の表現方法の使用にどのように影響するか、および MI のいくつかの制限について説明しています。 これらの制限の一部は、C++ の一般的な制限です。 他のユーザーは、MFC アーキテクチャによって課されます。

このテクニカルノートの最後には、MI を使用する完全な MFC アプリケーションがあります。

## <a name="cruntimeclass"></a>CRuntimeClass

MFC の永続化および動的オブジェクト作成メカニズムでは、 [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) データ構造体を使用してクラスを一意に識別します。 MFC は、これらの構造体の1つを、アプリケーション内の各動的またはシリアル化可能なクラスに関連付けます。 これらの構造体は、アプリケーションを起動するときに、型の特殊な静的オブジェクトを使用して初期化され `AFX_CLASSINIT` ます。

の現在の実装 `CRuntimeClass` では、MI ランタイム型情報はサポートされていません。 これは、MFC アプリケーションで MI を使用できないという意味ではありません。 ただし、複数の基底クラスを持つオブジェクトを操作する場合は、特定の責任があります。

[CObject:: IsKindOf](../mfc/reference/cobject-class.md#iskindof)メソッドでは、複数の基底クラスがある場合、オブジェクトの型を正しく判断できません。 したがって、 [cobject](../mfc/reference/cobject-class.md) を仮想基底クラスとして使用することはできません。また、 `CObject` C++ が適切な関数呼び出しを明確に区別できるように、Cobject [:: Serialize](../mfc/reference/cobject-class.md#serialize) や [cobject:: operator new](../mfc/reference/cobject-class.md#operator_new) などのメンバー関数へのすべての呼び出しにはスコープ修飾子が必要です。 プログラムが MFC 内で MI を使用する場合、基底クラスを含むクラスは、 `CObject` 基底クラスのリストの一番左のクラスである必要があります。

別の方法として、演算子を使用することも **`dynamic_cast`** できます。 MI を使用してオブジェクトを基底クラスの1つにキャストすると、コンパイラは、指定された基底クラスの関数を強制的に使用します。 詳細については、「 [Dynamic_cast 演算子](../cpp/dynamic-cast-operator.md)」を参照してください。

## <a name="cobject---the-root-of-all-classes"></a>CObject-すべてのクラスのルート

すべての重要なクラスは、クラスから直接または間接的に派生 `CObject` します。 `CObject` にはメンバーデータはありませんが、既定の機能がいくつかあります。 MI を使用する場合は、通常、2つ以上 `CObject` の派生クラスから継承します。 次の例は、クラスが [CFrameWnd](../mfc/reference/cframewnd-class.md) と [CObList](../mfc/reference/coblist-class.md)から継承する方法を示しています。

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

この例で `CObject` は、が2回含まれています。 これは、メソッドまたは演算子への参照を明確に区別する方法が必要であることを意味し `CObject` ます。 **Operator new** と [operator delete](../mfc/reference/cobject-class.md#operator_delete)は、2つの演算子を明確する必要があります。 別の例として、コンパイル時に次のコードを実行するとエラーが発生します。

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>CObject メソッドの再実装

2つ以上の派生基底クラスを持つ新しいクラスを作成する場合は、 `CObject` `CObject` 他のユーザーが使用するメソッドを再実装する必要があります。 演算子 **`new`** と **`delete`** は必須であり、 [Dump](../mfc/reference/cobject-class.md#dump) をお勧めします。 次の例では、 **`new`** and 演算子とメソッドを再実装してい **`delete`** `Dump` ます。

```cpp
class CListWnd : public CFrameWnd, public CObList
{
public:
    void* operator new(size_t nSize)
    {
        return CFrameWnd:: operator new(nSize);
    }
    void operator delete(void* p)
    {
        CFrameWnd:: operator delete(p);
    }
    void Dump(CDumpContent& dc)
    {
        CFrameWnd::Dump(dc);
        CObList::Dump(dc);
    }
    // ...
};
```

## <a name="virtual-inheritance-of-cobject"></a>CObject の仮想継承

実質的に継承することで、 `CObject` 関数のあいまいさに関する問題が解決しますが、そうではないように思えるかもしれません。 にはメンバーデータがないため `CObject` 、基底クラスのメンバーデータの複数のコピーを防ぐために、仮想継承は必要ありません。 前に示した最初の例では、 `Dump` 仮想メソッドはとで異なる方法で実装されているため、まだあいまいです `CFrameWnd` `CObList` 。 あいまいさを解消する最善の方法は、前のセクションで説明した推奨事項に従うことです。

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject:: IsKindOf と Run-Time の入力

の MFC でサポートされている実行時の入力機構では、 `CObject` マクロ DECLARE_DYNAMIC、IMPLEMENT_DYNAMIC、DECLARE_DYNCREATE、IMPLEMENT_DYNCREATE、DECLARE_SERIAL、および IMPLEMENT_SERIAL を使用します。 これらのマクロは、実行時の型チェックを実行して、安全なダウンキャストを保証できます。

これらのマクロは1つの基底クラスのみをサポートし、継承されたクラスを乗算するための制限付きの方法で動作します。 IMPLEMENT_DYNAMIC または IMPLEMENT_SERIAL で指定する基底クラスは、最初 (または一番左) の基底クラスである必要があります。 この配置では、最上位の基底クラスに対してのみ型チェックを行うことができます。 ランタイム型システムでは、追加の基底クラスについては何も認識されません。 次の例では、ランタイムシステムは型チェックを実行し `CFrameWnd` ますが、については何も認識しません `CObList` 。

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd とメッセージマップ

MFC メッセージマップシステムが正常に動作するには、次の2つの追加要件があります。

- 派生した基底クラスは1つだけである必要があり `CWnd` ます。

- 派生した `CWnd` 基底クラスは、最初 (または一番左) の基底クラスである必要があります。

次に、使用できない例をいくつか示します。

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>MI を使用したサンプルプログラム

次のサンプルは、と CWinApp から派生した1つのクラスで構成されるスタンドアロンアプリケーションです `CFrameWnd` 。 [](../mfc/reference/cwinapp-class.md) この方法でアプリケーションを構築することはお勧めしませんが、これは、1つのクラスを持つ最小の MFC アプリケーションの例です。

```cpp
#include <afxwin.h>

class CHelloAppAndFrame : public CFrameWnd, public CWinApp
{
public:
    CHelloAppAndFrame() {}

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

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
