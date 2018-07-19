---
title: 集計とクラス ファクトリに関するマクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_AGGREGATABLE
- atlcom/ATL::DECLARE_CLASSFACTORY
- atlcom/ATL::DECLARE_CLASSFACTORY_EX
- atlcom/ATL::DECLARE_CLASSFACTORY_AUTO_THREAD
- atlcom/ATL::DECLARE_CLASSFACTORY_SINGLETON
- atlcom/ATL::DECLARE_GET_CONTROLLING_UNKNOWN
- atlcom/ATL::DECLARE_NOT_AGGREGATABLE
- atlcom/ATL::DECLARE_ONLY_AGGREGATABLE
- atlcom/ATL::DECLARE_POLY_AGGREGATABLE
- atlcom/ATL::DECLARE_PROTECT_FINAL_CONSTRUCT
- atlcom/ATL::DECLARE_VIEW_STATUS
dev_langs:
- C++
helpviewer_keywords:
- class factories, ATL macros
- aggregation [C++], ATL macros
ms.assetid: d99d379a-0eec-481f-8daa-252dac18f163
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4995779a7f5595eca9dc47a29ea11d875995e959
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881228"
---
# <a name="aggregation-and-class-factory-macros"></a>集計とクラス ファクトリに関するマクロ
これらのマクロは、および集計を制御するためのクラス ファクトリを宣言する方法を提供します。  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|オブジェクトができることを宣言します (既定値) を集計します。|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|宣言するクラス ファクトリ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)ATL の既定のクラス ファクトリ。|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|クラス ファクトリをクラス ファクトリ オブジェクトを宣言します。|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|宣言[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)クラス ファクトリを使用します。|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|宣言[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリを使用します。|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|宣言[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)クラス ファクトリを使用します。|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|仮想宣言`GetControllingUnknown`関数。|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|オブジェクトを集約できないことを宣言します。|  
|[集約](#declare_only_aggregatable)|オブジェクトを集約する必要があることを宣言します。|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|不明な外部の値をチェックし、集計または集計可能でない、必要に応じて、オブジェクトを宣言します。|  
|[アグリゲート](#declare_protect_final_construct)|内部オブジェクトの構築時に削除されないように、外側のオブジェクトを保護します。|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|コンテナーにな VIEWSTATUS フラグを指定します。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
   
##  <a name="declare_aggregatable"></a>  DECLARE_AGGREGATABLE  
 オブジェクトを集計できることを指定します。  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集約可能として定義するクラスの名前。  
  
### <a name="remarks"></a>Remarks  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)既定の集計のモデルを指定するには、このマクロが含まれています。 この既定の設定を無効にするには、いずれかを指定、 [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)または[集約](#declare_only_aggregatable)クラスの定義でマクロ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>  DECLARE_CLASSFACTORY  
 宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)クラス ファクトリを使用します。  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>Remarks  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)このマクロを使用して、オブジェクトの既定のクラス ファクトリを宣言します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>  CComClassFactory クラス  
 このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイス。  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Remarks  
 `CComClassFactory` 実装して、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスより迅速に作成する新しいオブジェクトを許可するメモリ内のクラス ファクトリをロックするほか、CLSID が特定のオブジェクトを作成するためのメソッドが含まれています。 `IClassFactory` CLSID を割り当てることをシステム レジストリに登録するすべてのクラスを実装する必要があります。  
  
 ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言する`CComClassFactory`既定のクラス ファクトリとして。 この既定の設定を無効にする、DECLARE_CLASSFACTORY のいずれかを指定*XXX*クラスの定義でマクロ。 たとえば、 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)マクロは、クラス ファクトリの指定したクラスを使用します。  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 上記のクラス定義を指定する`CMyClassFactory`オブジェクトの既定のクラス ファクトリとして使用されます。 `CMyClassFactory` 派生する必要があります`CComClassFactory`オーバーライドと`CreateInstance`します。  
  
 ATL には、クラス ファクトリを宣言するその他の 3 つのマクロが用意されています。  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2)使用[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)ライセンスでの作成を制御します。  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)使用[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)、複数のアパートメント オブジェクトを作成します。  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)使用[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)、1 つを構築する[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクト。  
  
##  <a name="declare_classfactory_ex"></a>  DECLARE_CLASSFACTORY_EX  
 宣言`cf`クラス ファクトリを使用します。  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>パラメーター  
 *cf*  
 [in]クラス ファクトリ オブジェクトを実装するクラスの名前。  
  
### <a name="remarks"></a>Remarks  
 *Cf*パラメーターがから派生する必要があります[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)をオーバーライドし、`CreateInstance`メソッド。  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するには、マクロ`CComClassFactory`既定のクラス ファクトリとして。 ただし、しかし、オブジェクトのクラス定義に含めると、この既定をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>  DECLARE_CLASSFACTORY2  
 宣言[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)クラス ファクトリを使用します。  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>パラメーター  
 *使用許諾契約書*  
 [in]実装するクラス`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`します。  
  
### <a name="remarks"></a>Remarks  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するには、マクロ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、オブジェクトのクラス定義で DECLARE_CLASSFACTORY2 マクロを含めることでは、この既定をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>  CComClassFactory2 クラス  
 このクラスは、実装、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイス。  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>パラメーター  
 *ライセンス*  
 次の静的関数を実装するクラス。  
  
- **静的な BOOL VerifyLicenseKey (BSTR** `bstr` **)。**  
  
- **静的な BOOL GetLicenseKey (DWORD** `dwReserved` **、BSTR\***  `pBstr` **)。**  
  
- **静的な BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>Remarks  
 `CComClassFactory2` 実装して、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイスで、拡張機能の[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)します。 `IClassFactory2` コントロール オブジェクトのライセンスで作成します。 ライセンスされたコンピューターで実行するクラス ファクトリと、実行時のライセンス キーを提供できます。 このライセンス キーにより、完全なマシンのライセンスが存在しない場合は、オブジェクトをインスタンス化するアプリケーションです。  
  
 ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言する[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactory2`、指定、 [DECLARE_CLASSFACTORY2](#declare_classfactory2)オブジェクトのクラス定義でマクロ。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 `CMyLicense`、テンプレート パラメーターを`CComClassFactory2`、静的関数を実装する必要があります`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`します。 単純なライセンス クラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2` 両方から派生した`CComClassFactory2Base`と*ライセンス*します。 `CComClassFactory2Base`、から派生、`IClassFactory2`と**CComObjectRootEx\< CComGlobalsThreadModel >** します。  
  
##  <a name="declare_classfactory_auto_thread"></a>  DECLARE_CLASSFACTORY_AUTO_THREAD  
 宣言[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリを使用します。  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>Remarks  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するには、マクロ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、しかし、オブジェクトのクラス定義に含めると、この既定をオーバーライドします。  
  
 ときにオブジェクトを作成する (アウト プロセス サーバーで)、複数のアパートメント内で、クラスにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>  CComClassFactoryAutoThread クラス  
 このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイス、およびオブジェクトを複数のアパートメントを作成できます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>Remarks  
 `CComClassFactoryAutoThread` ような[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)が複数のアパートメント内に作成するオブジェクトを許可します。 このサポートを利用する、EXE のモジュールから派生させる[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言する[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactoryAutoThread`、指定、 [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)オブジェクトのクラス定義でマクロ。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>  DECLARE_CLASSFACTORY_SINGLETON  
 宣言[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)クラス ファクトリを使用します。  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>パラメーター  
 *obj*  
 [in]クラスのオブジェクトの名前。  
  
### <a name="remarks"></a>Remarks  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するには、マクロ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、しかし、オブジェクトのクラス定義に含めると、この既定をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>  CComClassFactorySingleton クラス  
 このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 1 つのオブジェクトを構築します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 クラス。  
  
 `CComClassFactorySingleton` 派生した[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 1 つのオブジェクトを構築します。 呼び出しごとに、`CreateInstance`メソッドは単にインターフェイス ポインターをこのオブジェクトを照会します。  
  
### <a name="remarks"></a>Remarks  
 ATL オブジェクトから派生することによって、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)します。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言する`CComClassFactory`既定のクラス ファクトリとして。 使用する`CComClassFactorySingleton`、指定、 [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)オブジェクトのクラス定義でマクロ。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>  DECLARE_GET_CONTROLLING_UNKNOWN  
 仮想関数を宣言`GetControllingUnknown`します。  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>Remarks  
 コンパイラのエラー メッセージを取得する場合、このマクロをオブジェクトに追加`GetControllingUnknown`が定義されていません (たとえば、 `CComAggregateCreator`)。  
  
##  <a name="declare_not_aggregatable"></a>  DECLARE_NOT_AGGREGATABLE  
 オブジェクトを集約できないことを指定します。  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計可能でないとして定義するクラスのオブジェクトの名前。  
  
### <a name="remarks"></a>Remarks  
 DECLARE_NOT_AGGREGATABLE により`CreateInstance`が試みられた場合は、エラー (CLASS_E_NOAGGREGATION) を返すよう、オブジェクトに集計します。  
  
 既定では、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_AGGREGATABLE](#declare_aggregatable)マクロで、オブジェクトを集計できることを指定します。 この既定の動作をオーバーライドするには、クラスの定義で DECLARE_NOT_AGGREGATABLE を含めます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>  集約  
 オブジェクトを集計する必要がありますを指定します。  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計をのみとして定義するクラスのオブジェクトの名前。  
  
### <a name="remarks"></a>Remarks  
 集約と (E_FAIL) エラーが発生する試みられた場合`CoCreate`オブジェクトとして。  
  
 既定では、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_AGGREGATABLE](#declare_aggregatable)マクロで、オブジェクトを集計できることを指定します。 この既定の動作をオーバーライドするには、クラスの定義で集約を含めます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>  DECLARE_POLY_AGGREGATABLE  
 指定のインスタンス**CComPolyObject \<**  *x* **>** オブジェクトが作成されるときに作成されます。  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計または集計可能でないとして定義するクラスのオブジェクトの名前。  
  
### <a name="remarks"></a>Remarks  
 作成時に、不明な外部の値がチェックされます。 NULL の場合`IUnknown`の非集計オブジェクトに実装されます。 不明な外部が NULL でない場合`IUnknown`集約オブジェクトに実装されます。  
  
 DECLARE_POLY_AGGREGATABLE を使用する利点は、両方を持つように`CComAggObject`と`CComObject`集計データおよび非集計のケースを処理するモジュールでします。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 つまり、モジュールで、vtable の 1 つだけのコピーと、関数の 1 つのコピーが存在します。 Vtable が大きい場合、モジュールのサイズが大幅に減りこのことができます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、モジュールのサイズを少し大きめにつながるは`CComAggObject`と`CComObject`します。  
  
 DECLARE_POLY_AGGREGATABLE マクロは、ATL コントロール ウィザードを使用するフル コントロールを作成する場合に自動的に、オブジェクトで宣言されます。  
  
##  <a name="declare_protect_final_construct"></a>  アグリゲート  

 削除されるオブジェクトを保護する (中に[finalconstruct 関数](ccomobjectrootex-class.md#finalconstruct)) 内部の集計されたオブジェクトが、数を 0 にデクリメントして参照カウントをインクリメントします。  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>  DECLARE_VIEW_STATUS  
 ATL の ActiveX コントロールのコントロールのクラスをコンテナーにな VIEWSTATUS フラグを指定するには、このマクロを配置します。  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>パラメーター  
 *statusFlags*  
 [in]な VIEWSTATUS フラグ。 参照してください[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)フラグの一覧についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
