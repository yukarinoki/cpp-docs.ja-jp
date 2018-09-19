---
title: 実行時のオブジェクト モデル サービス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 138275468801f3db2f2c64f06e5a505c412723b5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050958"
---
# <a name="run-time-object-model-services"></a>ランタイム オブジェクト モデル サービス
クラスは、 [CObject](../../mfc/reference/cobject-class.md)と[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)ランタイム クラス情報をシリアル化、および動的オブジェクトの作成へのアクセスなど、複数のサービスのオブジェクトをカプセル化します。 すべてのクラスから派生した`CObject`この機能を継承します。  
  
 ランタイム クラス情報へのアクセスには、実行時に、オブジェクトのクラスに関する情報を決定することができます。 実行時にオブジェクトのクラスを特定する機能は、余分な型チェック関数の引数を使用して、オブジェクトのクラスに基づく特殊なコードを記述する必要がある必要がある場合に便利です。 ランタイム クラス情報は、C++ 言語で直接サポートされていません。  
  
 シリアル化は、ファイルからの書き込みまたはまたはオブジェクトの内容を読み取り中のプロセスです。 シリアル化を使用して、アプリケーションの終了後も、オブジェクトの内容を格納することができます。 オブジェクト、アプリケーションが再起動したときに、ファイルから読み取ることができます。 このようなデータ オブジェクトは「固定」と呼ばれます  
  
 動的オブジェクトの作成には、実行時に指定したクラスのオブジェクトを作成することができます。 たとえば、ドキュメント、ビュー、およびフレーム オブジェクトする必要があります作成をサポートして動的フレームワークは、それらを動的に作成する必要があるため。  
  
 次の表では、ランタイム クラス情報をシリアル化、および動的な作成をサポートする MFC マクロを示します。  
  
 これらのサービスの実行時のオブジェクトとシリアル化する方法の詳細については、記事を参照してください。 [CObject クラス: クラス情報にアクセスする](../../mfc/accessing-run-time-class-information.md)します。  
  
### <a name="run-time-object-model-services-macros"></a>実行時のオブジェクト モデル サービス マクロ  
  


|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|(クラス宣言で使用する必要があります)、ランタイム クラス情報にアクセスできるようにします。|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|動的な作成および (クラス宣言で使用する必要があります)、ランタイム クラス情報へのアクセスを使用できます。|  
|[DECLARE_SERIAL](#declare_serial)|シリアル化および (クラス宣言で使用する必要があります)、ランタイム クラス情報へのアクセスを使用できます。|  
|[新規クラス](#implement_dynamic)|(クラスの実装で使用する必要があります)、ランタイム クラス情報にアクセスできるようにします。|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|動的な作成および実行時の情報 (クラスの実装で使用する必要があります) へのアクセスを使用できます。|  
|[IMPLEMENT_SERIAL](#implement_serial)|シリアル化および (クラスの実装で使用する必要があります)、ランタイム クラス情報へのアクセスを許可します。|  
|[RUNTIME_CLASS](#runtime_class)|返します、`CRuntimeClass`名前付きのクラスに対応する構造体。|  


 OLE には、頻繁に実行時にオブジェクトの動的生成が必要です。 たとえば、OLE サーバー アプリケーションは、クライアントからの要求に対する応答で OLE 項目を動的に作成できる必要があります。 同様に、オートメーション サーバーは、オートメーション クライアントからの要求に応答で項目を作成できる必要があります。  
  
 Microsoft Foundation Class ライブラリでは、OLE に特定の 2 つのマクロを提供します。  
  
### <a name="dynamic-creation-of-ole-objects"></a>OLE オブジェクトの動的な作成  

 






|||  
|-|-|  
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|コモン コントロール ライブラリが、指定された API を実装するかどうかを判断します。|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|コモン コントロール ライブラリが、指定された API を実装するかどうかを判断します。|
|[DECLARE_OLECREATE](#declare_olecreate)|OLE オートメーションを通じて作成されるオブジェクトを有効にします。|  
|[DECLARE_OLECTLTYPE](#declare_olectltype)|宣言、`GetUserTypeNameID`と`GetMiscStatus`コントロール クラスのメンバー関数。|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|OLE コントロールがそのプロパティを表示するプロパティ ページの一覧を提供することを宣言します。|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|OLE システムによって作成されるオブジェクトを有効にします。|  
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|実装、`GetUserTypeNameID`と`GetMiscStatus`コントロール クラスのメンバー関数。|  
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|このいずれかのマクロまたは[IMPLEMENT_OLECREATE](#implement_olecreate)を使用するクラスの実装ファイルに表示する必要があります`DECLARE_OLECREATE`します。 |

## <a name="afx_comctl32_if_exists"></a> AFX_COMCTL32_IF_EXISTS
コモン コントロール ライブラリが、指定された API を実装するかどうかを判断します。  
   
### <a name="syntax"></a>構文  
  ```  
AFX_COMCTL32_IF_EXISTS(  proc );  
```
### <a name="parameters"></a>パラメーター  
 *proc*  
 関数の名前を含む null で終わる文字列へのポインターまたは関数の序数値を指定します。 下位ワード; でこのパラメーターが、序数値である場合は、必要があります。上位ワードは、0 にする必要があります。 このパラメーターは、Unicode である必要があります。  
   
### <a name="remarks"></a>Remarks  
 指定された関数を一般的なコントロール ライブラリかどうかを判断するこのマクロを使用して*proc* (呼び出し元ではなく[GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212)します。  
   
### <a name="requirements"></a>要件  
 afxcomctl32.h、afxcomctl32.inl は  
   
### <a name="see-also"></a>関連項目  
 [MFC の一般的な分離のコントロール ライブラリ](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)
 
## <a name="afx_comctl32_if_exists2"></a>  AFX_COMCTL32_IF_EXISTS2
コモン コントロール ライブラリは、指定された API を実装するかどうかを決定します (これは Unicode バージョンの[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists))。  
   
### <a name="syntax"></a>構文    
```  
AFX_COMCTL32_IF_EXISTS2( proc );  
```
### <a name="parameters"></a>パラメーター  
 *proc*  
 関数の名前を含む null で終わる文字列へのポインターまたは関数の序数値を指定します。 下位ワード; でこのパラメーターが、序数値である場合は、必要があります。上位ワードは、0 にする必要があります。 このパラメーターは、Unicode である必要があります。  
   
### <a name="remarks"></a>Remarks  
 指定された関数を一般的なコントロール ライブラリかどうかを判断するこのマクロを使用して*proc* (呼び出し元ではなく[GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212)します。 このマクロは、AFX_COMCTL32_IF_EXISTS の Unicode バージョンです。  
   
### <a name="requirements"></a>要件  
 afxcomctl32.h、afxcomctl32.inl は  
   
### <a name="see-also"></a>関連項目  
 [MFC の一般的な分離のコントロール ライブラリ](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>  DECLARE_DYNAMIC  
 クラスを派生する場合、オブジェクトのクラスに関する実行時の情報にアクセスする機能を追加します。`CObject`します。  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>Remarks  
 DECLARE_DYNAMIC マクロをクラスのヘッダー (.h) モジュールに追加し、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールにそのモジュールを追加します。  
  
 RUNTIME_CLASS マクロを使用できますし、説明に従って DECLARE_ 動的および IMPLEMENT_DYNAMIC マクロを使用する場合、`CObject::IsKindOf`実行時に、オブジェクトのクラスを決定する関数。  
  
 DECLARE_DYNAMIC がクラス宣言に含まれる場合、クラスの実装で新規クラスを含める必要があります。  
  
 DECLARE_DYNAMIC マクロの詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 例をご覧ください[IMPLEMENT_DYNAMIC](#implement_dynamic)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="declare_dyncreate"></a>  DECLARE_DYNCREATE  
 オブジェクト`CObject`-実行時に動的に作成するためのクラスを派生します。  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>Remarks  
 フレームワークでは、この機能を使用して、新しいオブジェクトを動的に作成します。 たとえば、新しいビュー新しい文書を開くときに作成します。 ドキュメント、ビュー、およびフレーム クラスは、フレームワークが動的に作成する必要があるため、動的な作成をサポートする必要があります。  
  
 クラスの .h モジュールで DECLARE_DYNCREATE マクロを追加し、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールにそのモジュールを追加します。  
  
 DECLARE_DYNCREATE がクラス宣言に含まれる場合、クラスの実装で IMPLEMENT_DYNCREATE を含める必要があります。  
  
 DECLARE_DYNCREATE マクロの詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
> [!NOTE]
>  DECLARE_DYNCREATE マクロには、ヘッダーのすべての機能が含まれています。  
  
### <a name="example"></a>例  
 例をご覧ください[IMPLEMENT_DYNCREATE](#implement_dyncreate)します。  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

 
## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE
宣言、`GetUserTypeNameID`と`GetMiscStatus`コントロール クラスのメンバー関数。  
   
### <a name="syntax"></a>構文    
```
DECLARE_OLECTLTYPE( class_name )  
```
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 コントロール クラスの名前。  
   
### <a name="remarks"></a>Remarks  
 `GetUserTypeNameID` `GetMiscStatus`で宣言されている、純粋仮想関数`COleControl`します。 これらの関数は純粋であるため、仮想する必要があるクラスでオーバーライドされる、コントロール。 DECLARE_OLECTLTYPE、だけでなく、コントロール クラスの宣言に IMPLEMENT_OLECTLTYPE マクロを追加する必要があります。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
   
### <a name="see-also"></a>関連項目  
 [IMPLEMENT_OLECTLTYPE](#implement_olectltype)
 

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS
OLE コントロールがそのプロパティを表示するプロパティ ページの一覧を提供することを宣言します。  
   
### <a name="syntax"></a>構文    
```
DECLARE_PROPPAGEIDS( class_name )  
```
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 プロパティ ページを所有するコントロール クラスの名前。  
   
### <a name="remarks"></a>Remarks  
 使用して、`DECLARE_PROPPAGEIDS`クラスの宣言の最後にマクロ。 クラスのメンバー関数を定義する .cpp ファイルを使用して、`BEGIN_PROPPAGEIDS`マクロ、マクロのエントリの各コントロールのプロパティ ページで、`END_PROPPAGEIDS`プロパティ ページの一覧の末尾を宣言するマクロ。  
  
 プロパティ ページの詳細については、記事を参照してください。 [ActiveX コントロール: プロパティ ページ](../mfc-activex-controls-property-pages.md)します。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
   
### <a name="see-also"></a>関連項目   
 [BEGIN_PROPPAGEIDS](#begin_proppageids)   
 [END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>  DECLARE_SERIAL  
 必要な C++ ヘッダーのコードを生成、 `CObject`-シリアル化できるクラスを派生します。  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>Remarks  
 シリアル化は、ファイルからの書き込みまたはオブジェクトの内容を読み取り中のプロセスです。  
  
 DECLARE_SERIAL マクロを使用して、モジュール、および、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールでそのモジュールを含めます。  
  
 ストリームがクラス宣言に含まれる場合、クラスの実装で IMPLEMENT_SERIAL を含める必要があります。  
  
 DECLARE_SERIAL マクロには、ヘッダーとヘッダーのすべての機能が含まれています。  
  
 AFX_API マクロを使用して自動的にエクスポートすることができます、`CArchive`ストリーム マクロを使用するクラスの抽出演算子。 次のコードでクラス宣言 (.h ファイルにあります) を角かっこには。  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 DECLARE_SERIAL マクロの詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="implement_dynamic"></a>  新規クラス  
 動的なために必要な C++ コードを生成`CObject`-クラス名と、階層内の位置に、実行時アクセス権を持つクラスを派生します。  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
*base_class_name*<br/>
基底クラスの名前。  
  
### <a name="remarks"></a>Remarks  
 .Cpp モジュールで IMPLEMENT_DYNAMIC マクロを使用し、1 回だけ、結果のオブジェクト コードをリンクします。  
  
 詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="implement_dyncreate"></a>  IMPLEMENT_DYNCREATE  
 オブジェクト`CObject`-実行時に動的に作成するためのクラスを派生 DECLARE_DYNCREATE マクロを使用するとします。  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
 *base_class_name*  
 基底クラスの実際の名前。  
  
### <a name="remarks"></a>Remarks  
 フレームワークでは、この機能を使用して、新しいオブジェクトを動的に作成、たとえば、オブジェクトをシリアル化中にディスクから読み取るときにします。 クラスの実装ファイルには、IMPLEMENT_DYNCREATE マクロを追加します。 詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
 RUNTIME_CLASS マクロを使用できますし、ヘッダーと IMPLEMENT_DYNCREATE マクロを使用する場合、`CObject::IsKindOf`メンバー関数は、実行時に、オブジェクトのクラスを判別します。  
  
 DECLARE_DYNCREATE がクラス宣言に含まれる場合、クラスの実装で IMPLEMENT_DYNCREATE を含める必要があります。  
  
 このマクロ定義で、クラスの既定のコンス トラクターを呼び出すことに注意してください。 非自明なコンス トラクターはクラスによって明示的に実装されている場合にも明示的に既定コンス トラクターを実装する必要があります。 クラスの既定のコンス トラクターを追加することができます**プライベート**または**保護**メンバーのセクションでは、クラスの実装の外部から呼び出されるようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

## <a name="implement_olecreate_flags"></a>  IMPLEMENT_OLECREATE_FLAGS
このいずれかのマクロまたは[IMPLEMENT_OLECREATE](#implement_olecreate)ヘッダーを使用するクラスの実装ファイルに表示する必要があります。  
   
### <a name="syntax"></a>構文    
```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags, 
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
  
```
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
 *external_name*  
 (引用符で囲まれた) その他のアプリケーションに公開されるオブジェクトの名前。  
  
 *nFlags*  
 次のフラグの 1 つ以上含まれています。  
  
    -   `afxRegInsertable` OLE オブジェクトのオブジェクトの挿入 ダイアログ ボックスに表示するには、制御できます。    
    -   `afxRegApartmentThreading` ThreadingModel レジストリ内のスレッド処理モデルの設定アパートメントを = です。    
    -   `afxRegFreeThreading` スレッド処理モデルを ThreadingModel をレジストリに設定する Free を =。  
      
         2 つのフラグを結合する`afxRegApartmentThreading`と`afxRegFreeThreading`ThreadingModel を設定する = Both。 参照してください[InprocServer32](/windows/desktop/com/inprocserver32)スレッド モデルの登録の詳細については、Windows SDK に含まれています。 
   
 *l*、 *w1*、 *w2*、 *b1*、 *b2*、 *b3*、 *b4*、 *b5*、 *b6*、 *b7*、 *b8*  
 クラスの CLSID のコンポーネント。  
   
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  IMPLEMENT_OLECREATE_FLAGS を使用する場合は、スレッド処理モデルを使用して、オブジェクトがサポートを指定することができます、 *nFlags*パラメーター。 シングル スレッド モデルのみをサポートする場合は、IMPLEMENT_OLECREATE を使用します。  
  
 External name は、他のアプリケーションに公開されている識別子です。 クライアント アプリケーションでは、外部の名前を使用して、オートメーション サーバーからこのクラスのオブジェクトを要求します。  
  
 OLE クラス ID は、オブジェクトの一意の 128 ビット識別子です。 いずれかで構成されます**長い**、2 つ**WORD**秒、および 8**バイト**によって表される、s *l*、 *w1*、 *w2*、および*b1*を通じて*b8*構文の説明にします。 アプリケーション ウィザードとコード ウィザードでは、必要に応じての一意の OLE クラス Id を作成します。  
   
### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [DECLARE_OLECREATE](#declare_olecreate)   
 [CLSID キー](/windows/desktop/com/clsid-key-hklm)


## <a name="implement_olecreate"></a> IMPLEMENT_OLECTLTYPE
実装、`GetUserTypeNameID`と`GetMiscStatus`コントロール クラスのメンバー関数。  
   
### <a name="syntax"></a>構文    
```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )  
```
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 コントロール クラスの名前。  
  
 *idsUserTypeName*  
 コントロールの外部名を含む文字列のリソース ID。  
  
 *dwOleMisc*  
 1 つまたは複数のフラグを含む列挙です。 この列挙体の詳細については、次を参照してください。[入ります](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc)Windows SDK に含まれています。  
   
### <a name="remarks"></a>Remarks  
 IMPLEMENT_OLECTLTYPE、だけでなく、コントロール クラスの宣言に DECLARE_OLECTLTYPE マクロを追加する必要があります。  
  
 `GetUserTypeNameID`メンバー関数は、コントロール クラスを識別する、リソース文字列を返します。 `GetMiscStatus` コントロールの入りますビットを返します。 この列挙体には、コントロールの他の特性を説明する設定のコレクションを指定します。 入ります設定の詳細については、次を参照してください。[入ります](/windows/desktop/api/oleidl/ne-oleidl-tagolemisc)Windows SDK に含まれています。  
  
> [!NOTE]
>  ActiveX ControlWizard で使用される既定の設定: されて、OLEMISC_SETCLIENTSITEFIRST、OLEMISC_INSIDEOUT、OLEMISC_CANTLINKINSIDE、および OLEMISC_RECOMPOSEONRESIZE します。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>  IMPLEMENT_SERIAL  
 動的なために必要な C++ コードを生成`CObject`-クラス名と、階層内の位置に、実行時アクセス権を持つクラスを派生します。  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
 *base_class_name*  
 基底クラスの名前。  
  
 *wSchema*  
 UINT"バージョン"数を特定し、作成したデータの処理の逆シリアル化中のプログラムを有効にアーカイブにエンコードされるは、以前のバージョンをプログラムします。 クラスのスキーマの数は、-1 をすることはできません。  
  
### <a name="remarks"></a>Remarks  
 IMPLEMENT_SERIAL マクロを使用して、.cpp モジュールです。1 回だけ、結果のオブジェクト コードをリンクします。  
  
 AFX_API マクロを使用して自動的にエクスポートすることができます、`CArchive`ストリーム マクロを使用するクラスの抽出演算子。 次のコードでクラス宣言 (.h ファイルにあります) を角かっこには。  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 詳細については、次を参照してください。、 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 

##  <a name="runtime_class"></a>  RUNTIME_CLASS  
 C++ クラスの名前から、実行時のクラス構造体を取得します。  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 (引用符で囲まれていない) クラスの実際の名前。  
  
### <a name="remarks"></a>Remarks  
 Runtime_class へのポインターを[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)で指定されたクラスの構造体*class_name*します。 のみ`CObject`-DECLARE_DYNAMIC、ヘッダー、またはストリームに宣言された派生クラスへのポインターを返します、`CRuntimeClass`構造体。  
  
 詳細については、次を参照してください。 [CObject クラスのトピック](../../mfc/using-cobject.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afx.h 
   
##  <a name="declare_olecreate"></a>  DECLARE_OLECREATE  
 オブジェクト`CCmdTarget`-OLE オートメーションを使用して作成するためのクラスを派生します。  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
### <a name="remarks"></a>Remarks  
 このマクロは、この型のオブジェクトを作成するその他の OLE に対応したアプリケーションを使用できます。  
  
 クラスの .h モジュールで DECLARE_OLECREATE マクロを追加し、このクラスのオブジェクトへのアクセスが必要なすべての .cpp モジュールでそのモジュールを含めます。  
  
 クラス宣言でヘッダーが含まれる場合、クラスの実装で IMPLEMENT_OLECREATE を含める必要があります。 ヘッダーを使用して、クラス宣言には、DECLARE_DYNCREATE または DECLARE_SERIAL も使用する必要があります。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h  

##  <a name="implement_olecreate"></a>  IMPLEMENT_OLECREATE  
 このいずれかのマクロまたは[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)を使用するクラスの実装ファイルに表示する必要があります`DECLARE_OLECREATE`します。  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>パラメーター  
 *$class_name$*  
 クラスの実際の名前。  
  
 *external_name*  
 (引用符で囲まれた) その他のアプリケーションに公開されるオブジェクトの名前。  
  
 *l*、 *w1*、 *w2*、 *b1*、 *b2*、 *b3*、 *b4*、 *b5*、 *b6*、 *b7*、 *b8*  
 クラスの CLSID のコンポーネント。  
  
### <a name="remarks"></a>Remarks  
  
> [!NOTE]
>  既定では IMPLEMENT_OLECREATE を使用する場合は、1 つのスレッド モデルのみをサポートします。 IMPLEMENT_OLECREATE_FLAGS を使用する場合は、スレッド処理モデルを使用して、オブジェクトがサポートを指定することができます、 *nFlags*パラメーター。  
  
 External name は、他のアプリケーションに公開されている識別子です。 クライアント アプリケーションでは、外部の名前を使用して、オートメーション サーバーからこのクラスのオブジェクトを要求します。  
  
 OLE クラス ID は、オブジェクトの一意の 128 ビット識別子です。 いずれかで構成されます**長い**、2 つ**WORD**秒、および 8**バイト**によって表される、s *l*、 *w1*、 *w2*、および*b1*を通じて*b8*構文の説明にします。 アプリケーション ウィザードとコード ウィザードでは、必要に応じての一意の OLE クラス Id を作成します。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

