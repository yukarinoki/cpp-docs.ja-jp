---
title: 集計とクラス ファクトリ マクロ |Microsoft ドキュメント
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
ms.openlocfilehash: 8569d4ecbbd74a6d2d37701a4ec22e56cbe9f100
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366420"
---
# <a name="aggregation-and-class-factory-macros"></a>集計とクラス ファクトリ マクロ
これらのマクロは、クラス ファクトリを宣言および集計を制御する方法を提供します。  
  
|||  
|-|-|  
|[DECLARE_AGGREGATABLE](#declare_aggregatable)|オブジェクトができることを宣言しています (既定値) を集計します。|  
|[DECLARE_CLASSFACTORY](#declare_classfactory)|宣言するクラス ファクトリ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)ATL の既定のクラス ファクトリ。|  
|[DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)|クラス ファクトリをクラス ファクトリ オブジェクトを宣言します。|  
|[DECLARE_CLASSFACTORY2](#declare_classfactory2)|宣言[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)クラス ファクトリにします。|  
|[DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)|宣言[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリにします。|  
|[DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)|宣言[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)クラス ファクトリにします。|  
|[DECLARE_GET_CONTROLLING_UNKNOWN](#declare_get_controlling_unknown)|バーチャル マシンを宣言`GetControllingUnknown`関数。|  
|[DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)|オブジェクトを集計できないことを宣言します。|  
|[集約](#declare_only_aggregatable)|オブジェクトを集計する必要があることを宣言します。|  
|[DECLARE_POLY_AGGREGATABLE](#declare_poly_aggregatable)|外部の不明な値をチェックし、集計または集計可能でない、必要に応じて、オブジェクトを宣言します。|  
|[アグリゲート](#declare_protect_final_construct)|内部オブジェクトの構築時に削除されないように、外部オブジェクトを保護します。|  
|[DECLARE_VIEW_STATUS](#declare_view_status)|指定します、**な VIEWSTATUS**コンテナーへのフラグ。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="declare_aggregatable"></a>  DECLARE_AGGREGATABLE  
 オブジェクトを集計できることを指定します。  
  
```
DECLARE_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集約可能として定義するクラスの名前。  
  
### <a name="remarks"></a>コメント  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)既定集計モデルを指定するには、このマクロが含まれています。 この既定をオーバーライドするには、いずれかを指定、 [DECLARE_NOT_AGGREGATABLE](#declare_not_aggregatable)または[集約](#declare_only_aggregatable)クラスの定義でマクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_classfactory"></a>  DECLARE_CLASSFACTORY  
 宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)クラス ファクトリにします。  
  
```
DECLARE_CLASSFACTORY()
```  
  
### <a name="remarks"></a>コメント  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)このマクロを使用して、オブジェクトの既定のクラス ファクトリを宣言します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#55](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_2.h)]  
  
##  <a name="ccomclassfactory_class"></a>  CComClassFactory クラス  
 このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスです。  
  
```
class CComClassFactory : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>コメント  
 `CComClassFactory` 実装する、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイスで、特定の CLSID のオブジェクトを作成するだけでなく、クラス ファクトリをより迅速に作成する新しいオブジェクトを許可するメモリ内のロックのメソッドが含まれます。 **IClassFactory** CLSID 割り当てるして、システム レジストリを登録するすべてのクラスに実装する必要があります。  
  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言`CComClassFactory`既定のクラス ファクトリとして。 この既定をオーバーライドするには、いずれかを指定、 `DECLARE_CLASSFACTORY` *XXX*クラスの定義でマクロです。 たとえば、 [DECLARE_CLASSFACTORY_EX](#declare_classfactory_ex)マクロは、クラス ファクトリの指定したクラスを使用します。  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
 上記のクラス定義を指定する**CMyClassFactory**オブジェクトの既定のクラス ファクトリとして使用されます。 **CMyClassFactory**から派生する必要があります`CComClassFactory`オーバーライドと`CreateInstance`です。  
  
 ATL には、クラス ファクトリを宣言するその他の 3 つのマクロが用意されています。  
  
- [DECLARE_CLASSFACTORY2](#declare_classfactory2)使用[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)ライセンスを作成するコントロールします。  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)使用[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)、複数のアパートメント内でオブジェクトを作成します。  
  
- [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)使用[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)を構築する 1 つ[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)オブジェクト。  
  
##  <a name="declare_classfactory_ex"></a>  DECLARE_CLASSFACTORY_EX  
 宣言`cf`クラス ファクトリにします。  
  
```
DECLARE_CLASSFACTORY_EX( cf )
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 [in]クラス ファクトリ オブジェクトを実装するクラスの名前。  
  
### <a name="remarks"></a>コメント  
 `cf`パラメーターから派生しなければなりません[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)をオーバーライドし、`CreateInstance`メソッドです。  
  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するマクロ`CComClassFactory`既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY_EX`マクロ オブジェクトのクラス定義でこの既定値は無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_3.h)]  
  
##  <a name="declare_classfactory2"></a>  DECLARE_CLASSFACTORY2  
 宣言[CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)クラス ファクトリにします。  
  
```
DECLARE_CLASSFACTORY2( lic )
```  
  
### <a name="parameters"></a>パラメーター  
 *使用許諾契約書*  
 [in]実装するクラス`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`です。  
  
### <a name="remarks"></a>コメント  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するマクロ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY2`マクロ オブジェクトのクラス定義でこの既定値は無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
##  <a name="ccomclassfactory2_class"></a>  CComClassFactory2 クラス  
 このクラスは、実装、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)インターフェイスです。  
  
```
template <class license>
class  CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```    
  
### <a name="parameters"></a>パラメーター  
 *ライセンス*  
 次の静的関数を実装するクラス。  
  
- **静的な BOOL VerifyLicenseKey (BSTR** `bstr` **) です。**  
  
- **静的な BOOL GetLicenseKey (DWORD** `dwReserved` **、BSTR\***  `pBstr` **) です。**  
  
- **静的な BOOL IsLicenseValid ();**  
  
### <a name="remarks"></a>コメント  
 `CComClassFactory2` 実装する、 [IClassFactory2](http://msdn.microsoft.com/library/windows/desktop/ms692720)拡張機能であるインターフェイスの[IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)です。 **IClassFactory2**コントロール オブジェクトを介して、ライセンスを作成します。 ライセンスされたコンピューターで実行するクラス ファクトリと、実行時ライセンス キーを入力できます。 このライセンス キーには、コンピューターのフル ライセンスが存在しないときに、オブジェクトをインスタンス化するアプリケーションができます。  
  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactory2`を指定して、 [DECLARE_CLASSFACTORY2](#declare_classfactory2)オブジェクトのクラス定義でマクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_4.h)]  
  
 **CMyLicense**、テンプレート パラメーターを`CComClassFactory2`、静的関数を実装する必要があります`VerifyLicenseKey`、 `GetLicenseKey`、および`IsLicenseValid`です。 単純なライセンス クラスの例を次に示します。  
  
 [!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_5.h)]  
  
 `CComClassFactory2` 両方の派生**CComClassFactory2Base**と*ライセンス*です。 **CComClassFactory2Base**から派生、 **IClassFactory2**と**CComObjectRootEx\< CComGlobalsThreadModel >** です。  
  
##  <a name="declare_classfactory_auto_thread"></a>  DECLARE_CLASSFACTORY_AUTO_THREAD  
 宣言[CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)クラス ファクトリにします。  
  
```
DECLARE_CLASSFACTORY_AUTO_THREAD()
```  
  
### <a name="remarks"></a>コメント  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するマクロ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY_AUTO_THREAD`マクロ オブジェクトのクラス定義でこの既定値は無効にします。  
  
 アウト プロセス サーバーの場合) の「複数アパートメント内でオブジェクトを作成するときに追加`DECLARE_CLASSFACTORY_AUTO_THREAD`クラスにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="ccomclassfactoryautothread_class"></a>  CComClassFactoryAutoThread クラス  
 このクラスは、実装、 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)インターフェイス、およびオブジェクトが複数のアパートメント内で作成することができます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
class CComClassFactoryAutoThread : public IClassFactory,
public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
### <a name="remarks"></a>コメント  
 `CComClassFactoryAutoThread` ような[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)はオブジェクトを複数のアパートメント内で作成できるようにします。 このサポートを利用する、EXE モジュールから派生させる[は](../../atl/reference/ccomautothreadmodule-class.md)します。  
  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 使用する`CComClassFactoryAutoThread`を指定して、 [DECLARE_CLASSFACTORY_AUTO_THREAD](#declare_classfactory_auto_thread)オブジェクトのクラス定義でマクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#9](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_6.h)]  
  
##  <a name="declare_classfactory_singleton"></a>  DECLARE_CLASSFACTORY_SINGLETON  
 宣言[CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)クラス ファクトリにします。  
  
```
DECLARE_CLASSFACTORY_SINGLETON( obj )
```  
  
### <a name="parameters"></a>パラメーター  
 `obj`  
 [in]クラスのオブジェクトの名前です。  
  
### <a name="remarks"></a>コメント  
 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_CLASSFACTORY](#declare_classfactory)を指定するマクロ[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)既定のクラス ファクトリとして。 ただし、含めることによって、`DECLARE_CLASSFACTORY_SINGLETON`マクロ オブジェクトのクラス定義でこの既定値は無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="ccomclassfactorysingleton_class"></a>  CComClassFactorySingleton クラス  
 このクラスから派生[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を 1 つのオブジェクトを構築します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 作成したクラス。  
  
 `CComClassFactorySingleton` 派生した[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)を使用して[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)を 1 つのオブジェクトを構築します。 呼び出しごとに、`CreateInstance`メソッドは、インターフェイス ポインターをこのオブジェクトを単に照会します。  
  
### <a name="remarks"></a>コメント  
 ATL オブジェクトから派生することで、クラス ファクトリを取得する通常[CComCoClass](../../atl/reference/ccomcoclass-class.md)です。 このクラスには、マクロが含まれています。 [DECLARE_CLASSFACTORY](#declare_classfactory)、宣言`CComClassFactory`既定のクラス ファクトリとして。 使用する`CComClassFactorySingleton`を指定して、 [DECLARE_CLASSFACTORY_SINGLETON](#declare_classfactory_singleton)オブジェクトのクラス定義でマクロです。 例えば:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_7.h)]  
  
##  <a name="declare_get_controlling_unknown"></a>  DECLARE_GET_CONTROLLING_UNKNOWN  
 仮想関数を宣言`GetControllingUnknown`です。  
  
```
DECLARE_GET_CONTROLLING_UNKNOWN()
```  
  
### <a name="remarks"></a>コメント  
 コンパイラ エラー メッセージが表示される場合、このマクロをオブジェクトに追加`GetControllingUnknown`が定義されていません (たとえば、 **CComAggregateCreator**)。  
  
##  <a name="declare_not_aggregatable"></a>  DECLARE_NOT_AGGREGATABLE  
 オブジェクトを集計できないことを指定します。  
  
```
DECLARE_NOT_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計可能でないとして定義するクラスのオブジェクトの名前です。  
  
### <a name="remarks"></a>コメント  
 `DECLARE_NOT_AGGREGATABLE` により`CreateInstance`にエラーが返されます ( **CLASS_E_NOAGGREGATION**) が試行された場合に、オブジェクトに集計します。  
  
 既定では、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_AGGREGATABLE](#declare_aggregatable)マクロで、オブジェクトを集計できることを指定します。 この既定の動作をオーバーライドするには`DECLARE_NOT_AGGREGATABLE`クラス定義にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#121](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_1.h)]  
  
##  <a name="declare_only_aggregatable"></a>  集約  
 オブジェクトを集計する必要がありますを指定します。  
  
```
DECLARE_ONLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計可能ではのみとして定義するクラスのオブジェクトの名前です。  
  
### <a name="remarks"></a>コメント  
 `DECLARE_ONLY_AGGREGATABLE` エラーが発生 ( **E_FAIL**) しようとした場合**CoCreate**オブジェクトとして。  
  
 既定では、 [CComCoClass](../../atl/reference/ccomcoclass-class.md)が含まれています、 [DECLARE_AGGREGATABLE](#declare_aggregatable)マクロで、オブジェクトを集計できることを指定します。 この既定の動作をオーバーライドするには`DECLARE_ONLY_AGGREGATABLE`クラス定義にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#125](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_8.h)]  
  
##  <a name="declare_poly_aggregatable"></a>  DECLARE_POLY_AGGREGATABLE  
 指定のインスタンス**CComPolyObject \<**  *x* **>** は、オブジェクトが作成されるときに作成します。  
  
```
DECLARE_POLY_AGGREGATABLE( x )
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 [in]集計または集計可能でないとして定義するクラスのオブジェクトの名前です。  
  
### <a name="remarks"></a>コメント  
 作成中に、外側の不明な値がチェックされます。 場合は**NULL**、 **IUnknown**非集約オブジェクトには実装されています。 外側の unknown がない場合**NULL**、 **IUnknown**集約オブジェクトには実装されています。  
  
 使用する利点`DECLARE_POLY_AGGREGATABLE`両方を避けることが`CComAggObject`と`CComObject`モジュールに、集計と非集計のケースに対処します。 1 つ`CComPolyObject`オブジェクトは両方のケースを処理します。 つまり、モジュールに vtable の 1 つだけのコピーと、関数のうちの 1 つのコピーが存在します。 Vtable が大きい場合は、モジュールのサイズを大幅に縮小このできます。 ただし、vtable が小さい場合を使用して`CComPolyObject`には、集計または非集約オブジェクトは、最適化されていないために、わずかに大きくモジュールのサイズになりますが`CComAggObject`と`CComObject`です。  
  
 `DECLARE_POLY_AGGREGATABLE`マクロはフル コントロールを作成する、ATL コントロール ウィザードを使用する場合、自動的に、オブジェクトの宣言します。  
  
##  <a name="declare_protect_final_construct"></a>  アグリゲート  

 削除されるオブジェクトを保護する (中に[FinalConstruct](ccomobjectrootex-class.md#finalconstruct)) 内部集計オブジェクトが、カウントを 0 にデクリメントして参照カウントをインクリメントします。  
  
```
DECLARE_PROTECT_FINAL_CONSTRUCT()
```  
  
##  <a name="declare_view_status"></a>  DECLARE_VIEW_STATUS  
 指定する、ATL の ActiveX コントロールのコントロール クラスにこのマクロを配置、**な VIEWSTATUS**コンテナーへのフラグ。  
  
```
DECLARE_VIEW_STATUS( statusFlags )
```  
  
### <a name="parameters"></a>パラメーター  
 `statusFlags`  
 [in]**な VIEWSTATUS**フラグ。 参照してください[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)フラグの一覧についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#126](../../atl/codesnippet/cpp/aggregation-and-class-factory-macros_9.h)]  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
