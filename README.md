This module is a test for the error encountered when enabled new base fields with a hook and enabling such a module through the UI, not drush:

## Example error:

```
Notice: Undefined index: ldap_user_puid_sid in Drupal\Core\Entity\Sql\SqlContentEntityStorage->loadFromSharedTables() (line 568 of
web/core/lib/Drupal/Core/Entity/Sql/SqlContentEntityStorage.php) #0 web/core/includes/bootstrap.inc(548): _drupal_error_handler_real(8, 'Undefined
index...', '...', 568, Array)
#1 web/core/lib/Drupal/Core/Entity/Sql/SqlContentEntityStorage.php(568): _drupal_error_handler(8, 'Undefined index...', '...', 568, Array)
#2 web/core/lib/Drupal/Core/Entity/Sql/SqlContentEntityStorage.php(481): Drupal\Core\Entity\Sql\SqlContentEntityStorage->loadFromSharedTables(Array, Array)
#3 web/core/lib/Drupal/Core/Entity/Sql/SqlContentEntityStorage.php(433): Drupal\Core\Entity\Sql\SqlContentEntityStorage->mapFromStorageRecords(Array)
#4 web/core/lib/Drupal/Core/Entity/Sql/SqlContentEntityStorage.php(399): Drupal\Core\Entity\Sql\SqlContentEntityStorage->getFromStorage(Array)
#5 web/core/lib/Drupal/Core/Entity/EntityStorageBase.php(242): Drupal\Core\Entity\Sql\SqlContentEntityStorage->doLoadMultiple(Array)
#6 web/core/lib/Drupal/Core/Entity/EntityStorageBase.php(212): Drupal\Core\Entity\EntityStorageBase->loadMultiple(Array)
#7 web/core/lib/Drupal/Core/Session/AccountProxy.php(186): Drupal\Core\Entity\EntityStorageBase->load('1')
#8 web/core/lib/Drupal/Core/Session/AccountProxy.php(54): Drupal\Core\Session\AccountProxy->loadUserEntity('1')
#9 web/core/lib/Drupal/Core/Session/AccountProxy.php(75): Drupal\Core\Session\AccountProxy->getAccount()
#10 web/core/modules/locale/src/LocaleLookup.php(115): Drupal\Core\Session\AccountProxy->getRoles()
#11 web/core/lib/Drupal/Core/Cache/CacheCollector.php(327): Drupal\locale\LocaleLookup->getCid()
#12 web/core/lib/Drupal/Core/Cache/CacheCollector.php(143): Drupal\Core\Cache\CacheCollector->lazyLoadCache()
#13 web/core/modules/locale/src/LocaleTranslation.php(118): Drupal\Core\Cache\CacheCollector->get('Custom block ty...')
#14 web/core/lib/Drupal/Core/StringTranslation/TranslationManager.php(97): Drupal\locale\LocaleTranslation->getStringTranslation('de', 'Custom block ty...', '')
#15 web/core/lib/Drupal/Core/StringTranslation/TranslationManager.php(145): Drupal\Core\StringTranslation\TranslationManager->getStringTranslation('de', 'Custom block ty...',
'')
#16 web/core/lib/Drupal/Core/StringTranslation/TranslationManager.php(117): Drupal\Core\StringTranslation\TranslationManager->doTranslate('Custom block ty...', Array)
#17 web/core/lib/Drupal/Core/StringTranslation/TranslatableMarkup.php(199):
Drupal\Core\StringTranslation\TranslationManager->translateString(Object(Drupal\Core\StringTranslation\TranslatableMarkup))
#18 web/core/lib/Drupal/Component/Utility/ToStringTrait.php(15): Drupal\Core\StringTranslation\TranslatableMarkup->render()
#19 web/core/lib/Drupal/Core/Entity/EntityType.php(682): Drupal\Core\StringTranslation\TranslatableMarkup->__toString()
#20 web/core/lib/Drupal/Core/Entity/ContentEntityBase.php(1161): Drupal\Core\Entity\EntityType->getBundleLabel()
#21 web/core/modules/block_content/src/Entity/BlockContent.php(155): Drupal\Core\Entity\ContentEntityBase::baseFieldDefinitions(Object(Drupal\Core\Entity\ContentEntityType))
#22 web/core/lib/Drupal/Core/Entity/EntityFieldManager.php(204): Drupal\block_content\Entity\BlockContent::baseFieldDefinitions(Object(Drupal\Core\Entity\ContentEntityType))
#23 web/core/lib/Drupal/Core/Entity/EntityFieldManager.php(171): Drupal\Core\Entity\EntityFieldManager->buildBaseFieldDefinitions('block_content')
#24 web/core/lib/Drupal/Core/Entity/EntityFieldManager.php(394): Drupal\Core\Entity\EntityFieldManager->getBaseFieldDefinitions('block_content')
#25 web/core/lib/Drupal/Core/Entity/EntityManager.php(154): Drupal\Core\Entity\EntityFieldManager->getFieldStorageDefinitions('block_content')
#26 web/core/lib/Drupal/Core/Extension/ModuleInstaller.php(225): Drupal\Core\Entity\EntityManager->getFieldStorageDefinitions('block_content')
#27 web/core/lib/Drupal/Core/ProxyClass/Extension/ModuleInstaller.php(83): Drupal\Core\Extension\ModuleInstaller->install(Array, true)
#28 web/core/modules/system/src/Form/ModulesListForm.php(451): Drupal\Core\ProxyClass\Extension\ModuleInstaller->install(Array)
#29 [internal function]: Drupal\system\Form\ModulesListForm->submitForm(Array, Object(Drupal\Core\Form\FormState))
#30 web/core/lib/Drupal/Core/Form/FormSubmitter.php(111): call_user_func_array(Array, Array)
#31 web/core/lib/Drupal/Core/Form/FormSubmitter.php(51): Drupal\Core\Form\FormSubmitter->executeSubmitHandlers(Array, Object(Drupal\Core\Form\FormState))
#32 web/core/lib/Drupal/Core/Form/FormBuilder.php(585): Drupal\Core\Form\FormSubmitter->doSubmitForm(Array, Object(Drupal\Core\Form\FormState))
#33 web/core/lib/Drupal/Core/Form/FormBuilder.php(314): Drupal\Core\Form\FormBuilder->processForm('system_modules', Array, Object(Drupal\Core\Form\FormState))
#34 web/core/lib/Drupal/Core/Controller/FormController.php(74): Drupal\Core\Form\FormBuilder->buildForm('system_modules', Object(Drupal\Core\Form\FormState))
#35 [internal function]: Drupal\Core\Controller\FormController->getContentResult(Object(Symfony\Component\HttpFoundation\Request), Object(Drupal\Core\Routing\RouteMatch))
#36 web/core/lib/Drupal/Core/EventSubscriber/EarlyRenderingControllerWrapperSubscriber.php(123): call_user_func_array(Array, Array)
#37 web/core/lib/Drupal/Core/Render/Renderer.php(574): Drupal\Core\EventSubscriber\EarlyRenderingControllerWrapperSubscriber->Drupal\Core\EventSubscriber\{closure}()
#38 web/core/lib/Drupal/Core/EventSubscriber/EarlyRenderingControllerWrapperSubscriber.php(124):
Drupal\Core\Render\Renderer->executeInRenderContext(Object(Drupal\Core\Render\RenderContext), Object(Closure))
#39 web/core/lib/Drupal/Core/EventSubscriber/EarlyRenderingControllerWrapperSubscriber.php(97):
Drupal\Core\EventSubscriber\EarlyRenderingControllerWrapperSubscriber->wrapControllerExecutionInRenderContext(Array, Array)
#40 [internal function]: Drupal\Core\EventSubscriber\EarlyRenderingControllerWrapperSubscriber->Drupal\Core\EventSubscriber\{closure}()
#41 vendor/symfony/http-kernel/HttpKernel.php(144): call_user_func_array(Object(Closure), Array)
#42 vendor/symfony/http-kernel/HttpKernel.php(64): Symfony\Component\HttpKernel\HttpKernel->handleRaw(Object(Symfony\Component\HttpFoundation\Request), 1)
#43 web/core/lib/Drupal/Core/StackMiddleware/Session.php(57): Symfony\Component\HttpKernel\HttpKernel->handle(Object(Symfony\Component\HttpFoundation\Request), 1, true)
#44 web/core/lib/Drupal/Core/StackMiddleware/KernelPreHandle.php(47): Drupal\Core\StackMiddleware\Session->handle(Object(Symfony\Component\HttpFoundation\Request), 1, true)
#45 web/core/modules/page_cache/src/StackMiddleware/PageCache.php(99): Drupal\Core\StackMiddleware\KernelPreHandle->handle(Object(Symfony\Component\HttpFoundation\Request), 1,
true)
#46 web/core/modules/page_cache/src/StackMiddleware/PageCache.php(78): Drupal\page_cache\StackMiddleware\PageCache->pass(Object(Symfony\Component\HttpFoundation\Request), 1,
true)
#47 web/core/lib/Drupal/Core/StackMiddleware/ReverseProxyMiddleware.php(47):
Drupal\page_cache\StackMiddleware\PageCache->handle(Object(Symfony\Component\HttpFoundation\Request), 1, true)
#48 web/core/lib/Drupal/Core/StackMiddleware/NegotiationMiddleware.php(50):
Drupal\Core\StackMiddleware\ReverseProxyMiddleware->handle(Object(Symfony\Component\HttpFoundation\Request), 1, true)
#49 vendor/stack/builder/src/Stack/StackedHttpKernel.php(23): Drupal\Core\StackMiddleware\NegotiationMiddleware->handle(Object(Symfony\Component\HttpFoundation\Request), 1,
true)
#50 web/core/lib/Drupal/Core/DrupalKernel.php(652): Stack\StackedHttpKernel->handle(Object(Symfony\Component\HttpFoundation\Request), 1, true)
#51 web/index.php(19): Drupal\Core\DrupalKernel->handle(Object(Symfony\Component\HttpFoundation\Request))
#52 {main}.                               
```