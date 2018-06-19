---
title: 'TN038: MFC OLE IUnknown の実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- aggregation macros [MFC]
- COM interfaces, base interface
- IUnknown interface
- END_INTERFACE_MAP macro [MFC]
- TN038
- BEGIN_INTERFACE_PART macro [MFC]
- DECLARE_INTERFACE_MAP macro [MFC]
- BEGIN_INTERFACE_MAP macro [MFC]
- OLE [MFC], implementing IUnknown interface
- METHOD_PROLOGUE macro [MFC]
- STDMETHOD macro [MFC]
- END_INTERFACE_PART macro [MFC]
- INTERFACE_PART macro
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e93c4e9d8707d3960e768b6929bb2b1c16d60b42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385478"
---
# <a name="tn038-mfcole-iunknown-implementation"></a>テクニカル ノート 38: MFC/OLE IUnknown の実装
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 OLE 2 の中核は、"OLE コンポーネント オブジェクト モデル (COM: Component Object Model)" です。 COM は、複数のオブジェクトが相互に協調して通信するための基準を定義しています。 この定義には、オブジェクトにメソッドをディスパッチする方法など、"オブジェクト" を外から見たときの詳細が含まれています。 COM にはまた、基底クラスが定義されています。COM 対応のクラスはすべてこのクラスから派生します。 この基本クラスは、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)です。 ただし、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)インターフェイスは、C++ クラスと呼ばれます、COM は、1 つの言語に固有ではありません-C や PASCAL など、COM オブジェクトのバイナリ形式をサポートするその他の言語で実装できます。  
  
 派生したすべてのクラスを指す OLE [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 「インターフェイス」として これは、重要な相違点「インターフェイス」など[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)伴ってなしの実装です。 この "インターフェイス" と呼ばれるクラスは、オブジェクト間の通信プロトコルだけを定義し、その具体的な実装は定義していません。 これは、システムの最大限の柔軟性を確保するためです。 MFC/C++ プログラムの既定の動作は、MFC (Microsoft Foundation Class) によって実装されます。  
  
 MFC の実装を理解する[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)このインターフェイスは、新機能をまず理解する必要があります。 簡易バージョン[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)を以下に定義します。  
  
```  
class IUnknown  
{  
public:  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;  
    virtual ULONG AddRef() = 0;  
    virtual ULONG Release() = 0;  
};  
```  
  
> [!NOTE]
>  この説明では、必要な呼び出し規約の詳細の一部 (`__stdcall` など) を省略しています。  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)メンバー関数は、オブジェクトのメモリ管理を制御します。 COM は、参照カウント スキームを使用してオブジェクトを追跡します。 C++ と異なり、オブジェクトが直接参照されることはありません。 COM オブジェクトは、常にポインターを通じて参照されます。 所有者が行われるときに、オブジェクトを解放するが、オブジェクトを使用して[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)(が不要になる従来の C++ オブジェクトのような delete 演算子を使用して) ではなくメンバーが呼び出されます。 参照カウント スキームを使用することで、単一オブジェクトに対する多重参照を管理できます。 実装[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)オブジェクトの参照カウント: オブジェクトは、参照カウントがゼロに達するまでは削除されません。  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)実装という観点から非常に単純です。 実装では次の処理を行うだけです。  
  
```  
ULONG CMyObj::AddRef()   
{   
    return ++m_dwRef;   
}  
 
ULONG CMyObj::Release()   
{   
    if (--m_dwRef == 0)   
 {  
    delete this;   
    return 0;  
 }  
    return m_dwRef;  
}  
```  
  
 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)メンバー関数がもう少し興味深いものです。 唯一のメンバー関数は、オブジェクトがあるにとってあまり重要ではありません[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)— はより多くの機能を提供するオブジェクトを通知する良いこと[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)提供します。 ここでは[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)役に立ちます。 QueryInterface を使用すると、1 つのオブジェクトが複数の "インターフェイス" を持つことができます。 通常、これらのインターフェイスはから派生[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)し、新しいメンバー関数を追加することで追加の機能を追加します。 COM インターフェイスでは、インターフェイス内でメンバー変数を宣言せず、メンバー関数はすべて純粋仮想として宣言します。 たとえば、オブジェクトに適用された  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 しかない場合、IPrintInterface を取得する、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)、呼び出す[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)を使用して、`IID`の**IPrintInterface**です。 `IID` は、インターフェイスを一意に識別する 128 ビットの数値です。 各インターフェイスには、開発者や OLE によって定義された `IID` があります。 場合`pUnk`へのポインター、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)オブジェクト、そこから、IPrintInterface を取得するコードがある可能性があります。  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
 (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();
pPrint->Release();
*// release pointer obtained via QueryInterface  
}  
```  
  
 とても簡単ですがされるように見えますが、両方、IPrintInterface をサポートするオブジェクトを実装する方法と[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)インターフェイスは単純な IPrintInterface がから直接派生したためここでは[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) —、IPrintInterface を実装することによって[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)は自動的にサポートします。 例えば:  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();
virtual void PrintObject();

};  
```  
  
 実装[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)はまったく同じにするとその実装されている上記です。 **Cprintobj::queryinterface**は次のようになります。  
  
```  
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
 {  
 *ppvObj = this;  
    AddRef();
return NOERROR;  
 }  
    return E_NOINTERFACE;  
}  
```  
  
 上のコード例に示すように、インターフェイス ID (IID) が認識された場合はポインターがオブジェクトに返され、認識されない場合はエラーが発生します。 正常に実行[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)が暗黙的[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)です。 もちろん、CEditObj::Print も実装する必要があります。 これは単純なため、IPrintInterface はから直接派生した、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)インターフェイスです。 ただし、2 つの異なるインターフェイスをサポートする場合は、両方から派生した[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)次を検討してください。  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 IEditInterface と IPrintInterface の両方をサポートするクラスは、C++ の多重継承を利用する方法も含めて、さまざまな方法で実装できますが、ここではクラスの入れ子を利用する方法を説明します。  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();

 
    HRESULT QueryInterface(REFIID iid,
    void**);

    ULONG AddRef();
ULONG Release();
DWORD m_dwRef;  
 
    class CPrintObj : public IPrintInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual HRESULT QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_printObj;  
 
    class CEditObj : public IEditInterface  
 {  
    public: 
    CEditPrintObj* m_pParent;  
    virtual ULONG QueryInterface(REFIID iid,
    void** ppvObj);

    virtual ULONG AddRef();
virtual ULONG Release();

 } m_editObj;  
};  
```  
  
 以下では、上記の実装全体が含まれています。  
  
```  
CEditPrintObj::CEditPrintObj()  
{  
    m_editObj.m_pParent = this;  
    m_printObj.m_pParent = this;  
}  
 
ULONG CEditPrintObj::AddRef()   
{   
    return ++m_dwRef;  
}  
 
CEditPrintObj::Release()  
{  
    if (--m_dwRef == 0)  
 {  
    delete this;  
    return 0;  
 }  
    return m_dwRef;  
}  
 
HRESULT CEditPrintObj::QueryInterface(REFIID iid,
    void** ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
 {  
 *ppvObj = &m_printObj;  
    AddRef();
return NOERROR;  
 }  
    else if (iid == IID_IEditInterface)  
 {  
 *ppvObj = &m_editObj;  
    AddRef();
return NOERROR;  
 }  
    return E_NOINTERFACE;  
}  
 
ULONG CEditPrintObj::CEditObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CEditObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CEditObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
 
ULONG CEditPrintObj::CPrintObj::AddRef()   
{   
    return m_pParent->AddRef();

}  
 
ULONG CEditPrintObj::CPrintObj::Release()   
{   
    return m_pParent->Release();

}  
 
HRESULT CEditPrintObj::CPrintObj::QueryInterface(
    REFIID iid,
    void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid,
    ppvObj);

}  
```  
  
 大部分、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)実装は、CEditPrintObj クラスに配置されます::ceditobj と ceditprintobj::cprintobj にコードを複製するのではなくです。 これにより、コードのサイズが圧縮され、バグを回避できます。 重要な点は IUnknown インターフェイスから呼び出す[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)任意のインターフェイスを取得する、オブジェクトがサポート、および各インターフェイスから同じ操作を実行することができます。 つまり、すべて[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)各インターフェイスから使用可能な関数はまったく同じ方法で動作する必要があります。 これらの埋め込みオブジェクトから "外側のオブジェクト" の実装を呼び出すために、バック ポインター (m_pParent) が使用されています。 m_pParent ポインターは CEditPrintObj コンストラクターで初期化されます。 CEditPrintObj::CPrintObj::PrintObject と CEditPrintObj::CEditObj::EditObject も同様に実装します。 オブジェクトの編集というたった 1 つの機能を追加するために、大きなコードを追加しました。 しかしインターフェイス内にメンバー関数が 1 つだけということはほとんどなく、この例の場合も、EditObject と PrintObject を 1 つのインターフェイスにまとめるのが普通です。  
  
 このように単純なシナリオを実現するために、詳細な説明と大きなコードが必要です。 しかし、MFC/OLE クラスという代替方法を使用することで、同じ機能を簡単に実現できます。 MFC 実装では、Windows メッセージのラップに使用されるメッセージ マップに似た方法を使用します。 この機能が呼び出された*インターフェイス マップ*は次のセクションで説明されています。  
  
## <a name="mfc-interface-maps"></a>MFC インターフェイス マップ  
 MFC/OLE には "インターフェイス マップ" の実装が含まれています。この実装は概念や実行方法が、MFC の "メッセージ マップ" や "ディスパッチ マップ" に似ています。 MFC インターフェイス マップには、次の基本機能があります。  
  
-   標準実装[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)に組み込ま、`CCmdTarget`クラスです。  
  
-   によって変更、参照カウントのメンテナンス[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)と[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)  
  
-   データ駆動機構[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)  
  
 また、インターフェイス マップは、次の拡張機能もサポートしています。  
  
-   集約可能な COM オブジェクトの作成機能  
  
-   COM オブジェクトの実装に他の集約オブジェクトを使用する機能  
  
-   これらの実装のフックや拡張  
  
 集計の詳細については、次を参照してください。、[集計](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx)トピックです。  
  
 MFC インターフェイス マップの基点は `CCmdTarget` クラスです。 `CCmdTarget` "*しました*"カウントだけでなく、メンバー関数に関連付けられているすべての参照、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)実装 (参照カウントがであるなど`CCmdTarget`)。 OLE COM をサポートするクラスを作成するには `CCmdTarget` の派生クラスを作成し、マクロや `CCmdTarget` メンバー関数を利用して必要なインターフェイスを実装します。 MFC 実装では、上の例で示したように各インターフェイスの実装で入れ子になったクラスが使用され、 IUnknown の標準実装によって簡略化されています。また、コード簡略化のために多くのマクロも用意されています。  
  
## <a name="interface-map-basics"></a>インターフェイス マップの基本  
  
#### <a name="to-implement-a-class-using-mfcs-interface-maps"></a>MFC インターフェイス マップを利用したクラスを作成するには  
  
1.  `CCmdTarget` クラスの直接派生クラスまたは間接派生クラスを作成します。  
  
2.  派生クラスで関数 `DECLARE_INTERFACE_MAP` を定義します。  
  
3.  サポートする各インターフェイスに対して、クラス定義でマクロ `BEGIN_INTERFACE_PART` とマクロ `END_INTERFACE_PART` を使用します。  
  
4.  実装ファイルの中で、マクロ `BEGIN_INTERFACE_MAP` と `END_INTERFACE_MAP` を使用してクラスのインターフェイス マップを定義します。  
  
5.  マクロ `INTERFACE_PART` とマクロ `BEGIN_INTERFACE_MAP` の間に、サポートする各 IID に対するマクロ `END_INTERFACE_MAP` を記述します。これによって、IID とそのクラスの中の特定の "部分" が対応付けられます。  
  
6.  入れ子になったクラスとして、サポートするインターフェイスを実装します。  
  
7.  親 (`METHOD_PROLOGUE` 派生オブジェクト) にアクセスするにはマクロ `CCmdTarget` を使用します。  
  
8. [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)、および[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)に委任することができます、`CCmdTarget`これらの関数の実装 (`ExternalAddRef`、 `ExternalRelease`、および`ExternalQueryInterface`)。  
  
 上の例の CPrintEditObj の場合は次のように実装できます。  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public: *// member data and member functions for CPrintEditObj go here  
 
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP() 
 
    BEGIN_INTERFACE_PART(EditObj,
    IEditInterface)  
    STDMETHOD_(void,
    EditObject)();
END_INTERFACE_PART(EditObj) 
 
    BEGIN_INTERFACE_PART(PrintObj,
    IPrintInterface)  
    STDMETHOD_(void,
    PrintObject)();
END_INTERFACE_PART(PrintObj) 
};  
```  
  
 この宣言によって `CCmdTarget` 派生クラスが作成されます。 マクロ `DECLARE_INTERFACE_MAP` はこのクラスがカスタム インターフェイス マップを持つことをフレームワークに対して宣言します。 また、マクロ `BEGIN_INTERFACE_PART` とマクロ `END_INTERFACE_PART` は入れ子になったクラスを定義します。上の例では、入れ子になったクラスは CEditObj と CPrintObj です。入れ子になったクラス名の先頭には X が付きます。これに対してグローバル クラス名の先頭には "C"、インターフェイス クラス名の先頭には "I" が付きます。 これらの入れ子になった 2 つのクラスのそれぞれに、入れ子になった 2 つのメンバー m_CEditObj と m_CPrintObj が作成されます。 マクロを自動的に宣言、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)、および[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)関数です。 したがってのみを宣言する関数は、このインターフェイスに特定。EditObject と PrintObject (OLE マクロ`STDMETHOD`が使用できるように`_stdcall`仮想キーワードが必要に応じて、ターゲット プラットフォームに提供されます)。  
  
 このクラスに対するインターフェイス マップを実装するには:  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj,
    CCmdTarget)  
    INTERFACE_PART(CPrintEditObj,
    IID_IPrintInterface,
    PrintObj)  
    INTERFACE_PART(CPrintEditObj,
    IID_IEditInterface,
    EditObj)  
END_INTERFACE_MAP()  
```  
  
 これにより IID_IPrintInterface IID と m_CPrintObj、IID_IEditInterface IID と m_CEditObj が関連付けられます。 `CCmdTarget`の実装[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) (`CCmdTarget::ExternalQueryInterface`) このマップを使用してに m_CPrintObj や m_CEditObj 要求されたときにポインターを返します。 `IID_IUnknown` に対するエントリをマップに含める必要はありません。`IID_IUnknown` が要求されると、マップの先頭のインターフェイス (この場合は m_CPrintObj) が使用されます。  
  
 場合でも、`BEGIN_INTERFACE_PART`マクロが自動的に宣言されている、 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)と[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)の関数は、まだ必要がありますそれらを実装します。  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalAddRef();

}  
 
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return pThis->ExternalRelease();

}  
 
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(
    REFIID iid,
    void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
 
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj,
    EditObj) *// code to "Edit" the object,
    whatever that means...  
}  
```  
  
 CEditPrintObj::CPrintObj の実装は、上の CEditPrintObj::CEditObj の定義に似ています。 ここに示した関数を自動的に生成するマクロを作成することも可能ですが (開発初期バージョンの MFC/OLE では実際に作成されていました)、マクロが複数行に展開される場合はブレークポイントの設定が難しくなります。 このため、コードは手動で展開されます。  
  
 フレームワーク実装のメッセージ マップを利用すると、次の作業が不要になります。  
  
-   QueryInterface の実装  
  
-   AddRef と Release の実装  
  
-   各インターフェイスに対するこれらの組み込みメソッドの宣言  
  
 フレームワーク内部でもメッセージ マップが使用されています。 このため、フレームワーク クラス (`COleServerDoc` など) の派生クラスを作成すると、そのクラスは自動的に数種類のインターフェイスを持つことになります。また、このインターフェイスを変更したり、まったく新しいインターフェイスに置き換えたりすることもできます。 これは、フレームワークが基底クラスからのインターフェイス マップの継承を完全にサポートしているためです。 このため、`BEGIN_INTERFACE_MAP` は第 2 パラメーターとして基底クラス名を必要とします。  
  
> [!NOTE]
>  通常は、MFC から埋め込みに特殊化したインターフェイスを継承しても、MFC の組み込み OLE インターフェイスの実装を再利用できません。 これができないための使用、`METHOD_PROLOGUE`包含へのアクセスを取得するマクロ`CCmdTarget`-派生オブジェクトを意味、*固定オフセット*、埋め込みオブジェクトからの`CCmdTarget`-派生オブジェクト。 たとえば `COleClientItem::XAdviseSink` では、MFC 実装から埋め込みの XMyAdviseSink を派生できません。これは XAdviseSink では、`COleClientItem` オブジェクトの先頭からのオフセット値が異なる値になるためです。  
  
> [!NOTE]
>  ただし、これらの関数に MFC の既定の動作を求めるときは、MFC 実装に処理を任せることができます。 これは `IOleInPlaceFrame` クラスで MFC 実装の `COleFrameHook` (XOleInPlaceFrame) によって行われます。このクラスは多くの関数に対して m_xOleInPlaceUIWindow に処理を任せます。 この設計は、多数のインターフェイスを含むオブジェクトの実行時サイズを小さくする目的で選択されます。この処理ではバック ポインター (前の m_pParent など) は不要です。  
  
### <a name="aggregation-and-interface-maps"></a>集約とインターフェイス マップ  
 MFC はスタンドアロンの COM オブジェクトのほかに、集約もサポートしています。 集約自体はここで説明するトピックが複雑すぎます。参照してください、[集計](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx)集計の詳細については、トピックです。 ここではフレームワークとインターフェイス マップに組み込まれている集約に限定して説明します。  
  
 集約の利用方法には、(1) 集約をサポートする COM オブジェクトの利用、(2) 集約の一部となることができるオブジェクトの作成の 2 種類があります。 これらの機能はそれぞれ "集約オブジェクトの利用" と "集約可能オブジェクトの作成" と呼ばれます。 MFC ではこの両方がサポートされています。  
  
### <a name="using-an-aggregate-object"></a>集約オブジェクトの利用  
 集約オブジェクトを使用するには、集約を QueryInterface 機構に結び付ける必要があります。 つまり、本体オブジェクトに最初から含まれているかのように集約オブジェクトを動作させる必要があります。 どのようにはオブジェクトを結び付けるに MFC インターフェイス マップ機構に加え、`INTERFACE_PART`マクロ、入れ子になったオブジェクトは、IID にマップされていることができますもオブジェクトを宣言する集計の一部として、`CCmdTarget`クラスを派生します。 宣言には、`INTERFACE_AGGREGATE` マクロを使用します。 メンバー変数を指定できます (をポインターである必要がありますが、 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)またはその派生クラス)、インターフェイス マップ機構に組み込むことはできます。 場合は、ポインターが NULL でない場合に`CCmdTarget::ExternalQueryInterface`が呼び出されると、フレームワークは自動的にオブジェクトを呼び出す集計の[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)場合、メンバー関数、`IID`要求は、ネイティブのいずれかの`IID`sサポートされている、`CCmdTarget`オブジェクト自体です。  
  
##### <a name="to-use-the-interfaceaggregate-macro"></a>マクロ INTERFACE_AGGREGATE を使用するには  
  
1.  集約オブジェクトへのポインター (`IUnknown*`) となるメンバー変数を宣言します。  
  
2.  インターフェイス マップにマクロ `INTERFACE_AGGREGATE` を記述します。このマクロでこのメンバー変数を名前で指定します。  
  
3.  適切な時点で (普通は `CCmdTarget::OnCreateAggregates` 内) このメンバー変数を NULL 値以外の値に初期化します。  
  
 例えば:  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();

 
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();

 
    DECLARE_INTERFACE_MAP() *// "native" interface part macros may be used here  
};  
 
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
 
BOOL CAggrExample::OnCreateAggregates()  
{ *// wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
    GetControllingUnknown(),
    CLSCTX_INPROC_SERVER,  
    IID_IUnknown, (LPVOID*)&m_lpAggrInner);

    if (m_lpAggrInner == NULL)  
    return FALSE; *// optionally,
    create other aggregate objects here  
    return TRUE;  
}  
 
BEGIN_INTERFACE_MAP(CAggrExample,
    CCmdTarget) *// native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample,
    m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 m_lpAggrInner 変数はコンストラクターによって NULL に初期化されます。 フレームワークの既定の実装に NULL メンバー変数を無視する[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)です。 集約オブジェクトは `OnCreateAggregates` で作成するのが適切です。 MFC 実装の `COleObjectFactory` 以外でオブジェクトを作成するときは、この関数を明示的に呼び出します。 `CCmdTarget::OnCreateAggregates` で集約オブジェクトを作成し、`CCmdTarget::GetControllingUnknown` を使用する理由は、集約可能オブジェクトの作成方法を解説する際に説明します。  
  
 上の方法を使用すると、オブジェクト本来のインターフェイスに加えて集約オブジェクトが持つすべてのインターフェイスを持つことができます。 集約オブジェクトがサポートするインターフェイスの一部だけを利用するには、`CCmdTarget::GetInterfaceHook` をオーバーライドします。 これにより、非常に低レベルは、 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)です。 通常は、集約オブジェクトがサポートするすべてのインターフェイスを使用します。  
  
### <a name="making-an-object-implementation-aggregatable"></a>集約可能なオブジェクト実装のための作業  
 実装を集約可能オブジェクトの[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)、および[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) "controlling unknown"に委任する必要があります つまり、オブジェクトの一部であることを任せる必要あります[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)、および[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)別のオブジェクトにもから派生した[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)です。 この "controlling unknown" はオブジェクトが作成されるときにオブジェクト対して指定されます。つまり、`COleObjectFactory` の実装に対して指定されることになります。 COleObjectFactory をこのように実装すると、若干のオーバーヘッドが発生するため、場合によっては適切でない場合もあります。このため、MFC ではこの処理はオプションとして選択できるようになっています。 オブジェクトを集約可能にするには、そのオブジェクトのコンストラクターから `CCmdTarget::EnableAggregation` を呼び出します。  
  
 オブジェクトで集約を使用するときは、適切な "controlling unknown" が集約オブジェクトに渡されるようにする必要があります。 通常この[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)集計が作成されるときに、ポインターがオブジェクトに渡されます。 たとえば、`CoCreateInstance` を使用してオブジェクトを作成すると、パラメーター pUnkOuter が "controlling unknown" になります。 正確な "controlling unknown" ポインターは、`CCmdTarget::GetControllingUnknown` を呼び出して取得できます。 しかし、コンストラクター中ではこの関数の戻り値は保証されません。 このため、集約オブジェクトは `CCmdTarget::OnCreateAggregates` をオーバーライドした関数の中でのみ作成することを推奨します。この中では (`GetControllingUnknown` 実装から作成されたものであっても) `COleObjectFactory` の戻り値は保証されます。  
  
 架空の参照カウントを作成または解放するときに、オブジェクトが正しい参照カウントを操作することも重要です。 これを保証するために、`ExternalAddRef` と `ExternalRelease` ではなく、必ず `InternalRelease` と `InternalAddRef` を呼び出すようにしてください。 集約をサポートするクラスで `InternalRelease` と `InternalAddRef` を呼び出すことはほとんどありません。  
  
### <a name="reference-material"></a>リファレンス マニュアル  
 独自のインターフェイスの定義や、フレームワークの OLE インターフェイスのオーバーライドなど、OLE の高度な機能を利用するときは、基盤となるインターフェイス マップ機構の使い方を理解しておく必要があります。  
  
 ここでは、このような高度な機能の実装に使用されるマクロと API について説明します。  
  
### <a name="ccmdtargetenableaggregation--function-description"></a>CCmdTarget::EnableAggregation - 関数の説明  
  
```  
 
void EnableAggregation();

 
```  
  
## <a name="remarks"></a>コメント  
 この種のオブジェクトについて OLE 集約をサポートする場合、この関数を派生クラスのコンストラクターで呼び出します。 この関数を呼び出すことによって、集約可能オブジェクトに必要な特別な IUnknown 実装が用意されます。  
  
### <a name="ccmdtargetexternalqueryinterface--function-description"></a>CCmdTarget::ExternalQueryInterface — 関数の説明  
  
```  
 
    DWORD ExternalQueryInterface(constvoidFAR* lpIID, LPVOIDFAR* ppvObj);
```  
  
## <a name="remarks"></a>コメント  
  
#### <a name="parameters"></a>パラメーター  
 `lpIID`  
 IID への far ポインター (QueryInterface の第 1 引数)  
  
 `ppvObj`  
 IUnknown* へのポインター (QueryInterface の第 2 引数)  
  
## <a name="remarks"></a>コメント  
 IUnknown を実装するとき、クラスが実装する各インターフェイスに対してこの関数を呼び出します。 この関数はオブジェクトのインターフェイス マップに基づき、標準的なデータ駆動型の QueryInterface を実行します。 この関数の戻り値は HRESULT 型にキャストする必要があります。 集約オブジェクトの場合、この関数はローカルなインターフェイス マップを使用せずに、"controlling IUnknown" を呼び出します。  
  
### <a name="ccmdtargetexternaladdref--function-description"></a>CCmdTarget::ExternalAddRef - 関数の説明  
  
```  
 
DWORD ExternalAddRef();

 
```  
  
## <a name="remarks"></a>コメント  
 IUnknown::AddRef を実装するとき、クラスが実装する各インターフェイスに対してこの関数を呼び出します。 戻り値は、CCmdTarget オブジェクトの新しい参照カウント値を示します。 集約オブジェクトの場合、この関数はローカルな参照カウントを操作せずに、"controlling IUnknown" を呼び出します。  
  
### <a name="ccmdtargetexternalrelease--function-description"></a>CCmdTarget::ExternalRelease - 関数の説明  
  
```  
 
DWORD ExternalRelease();

 
```  
  
## <a name="remarks"></a>コメント  
 IUnknown::Release を実装するとき、クラスが実装する各インターフェイスに対してこの関数を呼び出します。 戻り値は、オブジェクトの新しい参照カウント値を示します。 集約オブジェクトの場合、この関数はローカルな参照カウントを操作せずに、"controlling IUnknown" を呼び出します。  
  
### <a name="declareinterfacemap--macro-description"></a>DECLARE_INTERFACE_MAP - マクロの説明  
  
```  
 
DECLARE_INTERFACE_MAP  
 
```  
  
## <a name="remarks"></a>コメント  
 このマクロは、`CCmdTarget` からの派生クラスのうち、インターフェイス マップを持つすべてのクラスで使用します。 使用方法は `DECLARE_MESSAGE_MAP` と同じです。 このマクロ呼び出しは、クラス定義 (通常はヘッダー (.H) ファイル内) で使用します。 `DECLARE_INTERFACE_MAP` を指定したクラスでは、実装ファイル (.CPP) でマクロ `BEGIN_INTERFACE_MAP` と `END_INTERFACE_MAP` を使用してインターフェイス マップを定義する必要があります。  
  
### <a name="begininterfacepart-and-endinterfacepart--macro-descriptions"></a>BEGIN_INTERFACE_PART、END_INTERFACE_PART - マクロの説明  
  
```  
 
    BEGIN_INTERFACE_PART(
 localClass,   
    iface);

END_INTERFACE_PART(
 localClass)  
```  
  
## <a name="remarks"></a>コメント  
  
#### <a name="parameters"></a>パラメーター  
 `localClass`  
 このインターフェイスを実装するクラスの名前  
  
 `iface`  
 このクラスによって実装されるインターフェイスの名前  
  
## <a name="remarks"></a>コメント  
 クラスが実装するインターフェイスごとに、`BEGIN_INTERFACE_PART` と `END_INTERFACE_PART` のペアを記述する必要があります。 これらのマクロでは、OLE インターフェイスから派生させるローカル クラスと、そのクラスの埋め込みメンバー変数を定義します。 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)、[リリース](http://msdn.microsoft.com/library/windows/desktop/ms682317)、および[QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521)メンバーが自動的に宣言されます。 これ以外のメンバー関数をインターフェイスで使用する場合は、直接宣言する必要があります。これらの宣言はマクロ `BEGIN_INTERFACE_PART` と `END_INTERFACE_PART` の間に記述します。  
  
 引数 `iface` は作成する OLE インターフェイス (`IAdviseSink` や `IPersistStorage` など、またはカスタム インターフェイス) を示します。  
  
 引数 `localClass` に定義するローカル クラス名を指定します。 名前の先頭には 'X' が自動的に付けられます。 この名前付け規則は、グローバル クラス名との競合を回避するためです。 また埋め込みメンバーには `localClass` 名の前に 'm_x' を付けた名前が指定されます。  
  
 例えば:  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink,
    IAdviseSink)  
    STDMETHOD_(void,
    OnDataChange)(LPFORMATETC,
    LPSTGMEDIUM);

    STDMETHOD_(void,
    OnViewChange)(DWORD,
    LONG);

    STDMETHOD_(void,
    OnRename)(LPMONIKER);

 STDMETHOD_(void,
    OnSave)();
STDMETHOD_(void,
    OnClose)();

END_INTERFACE_PART(MyAdviseSink) 
```  
  
 これによって IAdviseSink から派生されるローカル クラス XMyAdviseSink が定義されます。またこのクラスのメンバー名は m_xMyAdviseSink になります。  
  
> [!NOTE]
>  始まる行`STDMETHOD`_ は基本的に OLE2 からコピーします。H あり、わずかに変更します。 OLE2.H からコピーすると、発見が困難なエラーを回避できます。  
  
### <a name="begininterfacemap-and-endinterfacemap--macro-descriptions"></a>BEGIN_INTERFACE_MAP、END_INTERFACE_MAP - マクロの説明  
  
```  
 
    BEGIN_INTERFACE_MAP(
 theClass,   
    baseClass)END_INTERFACE_MAP 
```  
  
## <a name="remarks"></a>コメント  
  
#### <a name="parameters"></a>パラメーター  
 `theClass`  
 定義するインターフェイス マップが含まれるクラス  
  
 `baseClass`  
 `theClass` の派生元のクラス。  
  
## <a name="remarks"></a>コメント  
 実際にインターフェイス マップを定義するには、実装ファイルにマクロ `BEGIN_INTERFACE_MAP` と `END_INTERFACE_MAP` を記述します。 実装するインターフェイスごとに 1 つ以上の `INTERFACE_PART` マクロを呼び出します。 このクラスで使用する集約ごとに 1 つの `INTERFACE_AGGREGATE` マクロ呼び出しを記述します。  
  
### <a name="interfacepart--macro-description"></a>INTERFACE_PART - マクロの説明  
  
```  
 
    INTERFACE_PART(
 theClass,   
    iid, 
    localClass) 
```  
  
## <a name="remarks"></a>コメント  
  
#### <a name="parameters"></a>パラメーター  
 `theClass`  
 インターフェイス マップを持つクラスの名前。  
  
 `iid`  
 埋め込みクラスに割り当てられる `IID`。  
  
 `localClass`  
 ローカル クラスの名前。'X' は付けません。  
  
## <a name="remarks"></a>コメント  
 このマクロはオブジェクトでサポートする各インターフェイスを定義する `BEGIN_INTERFACE_MAP` マクロと `END_INTERFACE_MAP` マクロの間で使用します。 このマクロは `theClass` と `localClass` で示されたクラスのメンバーに IID を割り当てます。 `localClass` の先頭には 'm_x' が自動的に追加されます。 1 個のメンバーに複数の `IID` を割り当てることもできます。 これは、"最派生" インターフェイスを 1 個だけ作成し、これをすべての中間インターフェイスとして使用するときにも役に立ちます。 この方法を使用した例が `IOleInPlaceFrameWindow` インターフェイスです。 このインターフェイスの階層構造は次のようになっています。  
  
```  
IUnknown  
    IOleWindow 
    IOleUIWindow 
    IOleInPlaceFrameWindow 
```  
  
 オブジェクトを実装する場合`IOleInPlaceFrameWindow`、クライアントが`QueryInterface`これらのインターフェイスのいずれかの: `IOleUIWindow`、 `IOleWindow`、または[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)、「最派生」インターフェイスだけでなく`IOleInPlaceFrameWindow`(1 つが実際には実装する)。 この適用を処理するには、複数の `INTERFACE_PART` マクロを使用して、すべての基本インターフェイスを `IOleInPlaceFrameWindow` インターフェイスに割り当てます。  
  
 クラス定義ファイルには次のように記述されます。  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 クラス実装ファイルには次のように記述されます。  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd,
    CFrameWnd)  
    INTERFACE_PART(CMyWnd,
    IID_IOleWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleUIWindow,
    MyFrameWindow)  
    INTERFACE_PART(CMyWnd,
    IID_IOleInPlaceFrameWindow,
    MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 IUnknown は常に必要であるため、フレームワークによって自動的にサポートされます。  
  
### <a name="interfacepart--macro-description"></a>INTERFACE_PART - マクロの説明  
  
```  
 
    INTERFACE_AGGREGATE(
 theClass,   
    theAggr) 
```  
  
## <a name="remarks"></a>コメント  
  
#### <a name="parameters"></a>パラメーター  
 `theClass`  
 インターフェイス マップを持つクラスの名前。  
  
 `theAggr`  
 集約するメンバー変数の名前。  
  
## <a name="remarks"></a>コメント  
 このマクロは、クラスが集約オブジェクトを使用することをフレームワークに知らせます。 このマクロは `BEGIN_INTERFACE_PART` マクロと `END_INTERFACE_PART` マクロの間に記述します。 集約オブジェクトが別のオブジェクトから派生した[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)です。 集約と `INTERFACE_AGGREGATE` マクロを使用すると、集約によってサポートされているすべてのインターフェイスを、オブジェクトによって直接サポートされているように見せることができます。 `theAggr`引数はから派生するクラスのメンバー変数の名前だけで[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) (直接または間接的に)。 `INTERFACE_AGGREGATE` マクロをインターフェイス マップの中に記述するときは、必ず `INTERFACE_PART` マクロの後に記述します。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

