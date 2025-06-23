import React, { useState, useEffect } from 'react';
import { Menu, X, ChevronRight, BarChart3, Shield, TrendingUp, Users, Package, Zap, Award, Globe, Check, ArrowRight, Star, Clock, Target, Sparkles } from 'lucide-react';

const FomtimeWebsite = () => {
  const [isMenuOpen, setIsMenuOpen] = useState(false);
  const [scrolled, setScrolled] = useState(false);
  const [activeStat, setActiveStat] = useState(0);

  useEffect(() => {
    const handleScroll = () => {
      setScrolled(window.scrollY > 20);
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  useEffect(() => {
    const interval = setInterval(() => {
      setActiveStat((prev) => (prev + 1) % 4);
    }, 3000);
    return () => clearInterval(interval);
  }, []);

  const stats = [
    { value: '500+', label: 'Premium Marka', icon: Award },
    { value: '10M+', label: 'Aylık İşlem', icon: TrendingUp },
    { value: '99.8%', label: 'Müşteri Memnuniyeti', icon: Star },
    { value: '2.5B₺', label: 'Yıllık Ciro', icon: BarChart3 }
  ];

  const services = [
    {
      icon: Package,
      title: 'Marka Yönetimi',
      description: 'E-ticaret platformlarında markanızı profesyonelce yönetiyoruz',
      features: ['Katalog optimizasyonu', 'Stok yönetimi', 'Fiyat stratejileri']
    },
    {
      icon: TrendingUp,
      title: 'Büyüme Stratejisi',
      description: 'Veriye dayalı büyüme stratejileri ile satışlarınızı artırıyoruz',
      features: ['Pazar analizi', 'Rekabet takibi', 'Büyüme planlaması']
    },
    {
      icon: Shield,
      title: 'Marka Koruması',
      description: 'Markanızı yetkisiz satıcılardan ve taklitlerden koruyoruz',
      features: ['Yasal koruma', 'İzleme sistemi', '7/24 takip']
    },
    {
      icon: Zap,
      title: 'Hızlı Operasyon',
      description: 'Lojistik ve operasyon süreçlerinizi optimize ediyoruz',
      features: ['Hızlı teslimat', 'Depo yönetimi', 'İade süreçleri']
    }
  ];

  const partnershipModels = [
    {
      title: 'Tam Yetki Modeli',
      description: 'Markanızın tüm e-ticaret operasyonlarını üstleniriz',
      features: ['Envanter satın alma', 'Komple yönetim', 'Garanti edilen satış'],
      color: 'from-purple-600 to-blue-600'
    },
    {
      title: 'Hibrit Model',
      description: 'Sizinle birlikte çalışarak optimal sonuçlar elde ederiz',
      features: ['Ortak planlama', 'Esnek yapı', 'Risk paylaşımı'],
      color: 'from-blue-600 to-cyan-600'
    },
    {
      title: 'Danışmanlık Modeli',
      description: 'Uzman ekibimizle markanıza özel stratejiler geliştiriririz',
      features: ['Strateji desteği', 'Eğitim programları', 'Performans takibi'],
      color: 'from-cyan-600 to-teal-600'
    },
    {
      title: 'Özel Çözüm',
      description: 'Markanıza özel ihtiyaçlarınıza göre model tasarlıyoruz',
      features: ['Kişiselleştirilmiş', 'Tam esneklik', 'Özel ekip'],
      color: 'from-teal-600 to-green-600'
    }
  ];

  const brands = [
    'Nike', 'Adidas', 'Apple', 'Samsung', 'Sony', 'LG', 'Philips', 'Bosch',
    'P&G', 'Unilever', 'L\'Oréal', 'Nestlé', 'Coca-Cola', 'PepsiCo', 'Microsoft', 'Google'
  ];

  return (
    <div className="min-h-screen bg-gradient-to-b from-gray-900 via-gray-900 to-black text-white">
      {/* Navigation */}
      <nav className={`fixed w-full z-50 transition-all duration-300 ${scrolled ? 'bg-gray-900/95 backdrop-blur-md shadow-2xl' : 'bg-transparent'}`}>
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center h-16">
            <div className="flex items-center">
              <div className="flex items-center space-x-2">
                <Sparkles className="h-8 w-8 text-cyan-400" />
                <span className="text-2xl font-bold bg-gradient-to-r from-cyan-400 to-blue-600 bg-clip-text text-transparent">FOMTIME</span>
              </div>
            </div>
            
            <div className="hidden md:flex items-center space-x-8">
              <a href="#home" className="hover:text-cyan-400 transition-colors">Ana Sayfa</a>
              <a href="#services" className="hover:text-cyan-400 transition-colors">Hizmetler</a>
              <a href="#brands" className="hover:text-cyan-400 transition-colors">Markalar</a>
              <a href="#partnership" className="hover:text-cyan-400 transition-colors">Ortaklık</a>
              <a href="#contact" className="hover:text-cyan-400 transition-colors">İletişim</a>
              <button className="bg-gradient-to-r from-cyan-500 to-blue-600 px-6 py-2 rounded-full hover:from-cyan-600 hover:to-blue-700 transition-all transform hover:scale-105">
                Hemen Başla
              </button>
            </div>

            <button onClick={() => setIsMenuOpen(!isMenuOpen)} className="md:hidden">
              {isMenuOpen ? <X className="h-6 w-6" /> : <Menu className="h-6 w-6" />}
            </button>
          </div>
        </div>

        {/* Mobile Menu */}
        {isMenuOpen && (
          <div className="md:hidden bg-gray-900/95 backdrop-blur-md">
            <div className="px-2 pt-2 pb-3 space-y-1">
              <a href="#home" className="block px-3 py-2 hover:bg-gray-800 rounded-md">Ana Sayfa</a>
              <a href="#services" className="block px-3 py-2 hover:bg-gray-800 rounded-md">Hizmetler</a>
              <a href="#brands" className="block px-3 py-2 hover:bg-gray-800 rounded-md">Markalar</a>
              <a href="#partnership" className="block px-3 py-2 hover:bg-gray-800 rounded-md">Ortaklık</a>
              <a href="#contact" className="block px-3 py-2 hover:bg-gray-800 rounded-md">İletişim</a>
            </div>
          </div>
        )}
      </nav>

      {/* Hero Section */}
      <section id="home" className="pt-16 min-h-screen flex items-center relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-br from-cyan-500/10 via-blue-600/10 to-purple-600/10 animate-pulse"></div>
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
          <div className="text-center">
            <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-cyan-400 via-blue-500 to-purple-600 bg-clip-text text-transparent animate-gradient">
              Markanız. Bizim Uzmanlığımız.
            </h1>
            <h2 className="text-4xl md:text-6xl font-bold mb-8">
              Durdurulamaz Büyüme.
            </h2>
            <p className="text-xl md:text-2xl text-gray-300 mb-12 max-w-3xl mx-auto">
              Premium markaların e-ticaret platformlarında kontrolü ele almasına, satışlarını hızlandırmasına ve karlılığını maksimize etmesine yardımcı oluyoruz.
            </p>
            <div className="flex flex-col sm:flex-row gap-4 justify-center">
              <button className="bg-gradient-to-r from-cyan-500 to-blue-600 px-8 py-4 rounded-full text-lg font-semibold hover:from-cyan-600 hover:to-blue-700 transition-all transform hover:scale-105 flex items-center justify-center">
                Ücretsiz Analiz <ArrowRight className="ml-2 h-5 w-5" />
              </button>
              <button className="border border-cyan-400 px-8 py-4 rounded-full text-lg font-semibold hover:bg-cyan-400/10 transition-all">
                Demo Talep Et
              </button>
            </div>
          </div>
        </div>
      </section>

      {/* Stats Section */}
      <section className="py-20 relative">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-4xl font-bold text-center mb-16">Rakamlarla FOMTIME</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
            {stats.map((stat, index) => {
              const Icon = stat.icon;
              return (
                <div 
                  key={index} 
                  className={`bg-gradient-to-br from-gray-800 to-gray-900 p-8 rounded-2xl text-center transform transition-all duration-500 ${
                    activeStat === index ? 'scale-110 shadow-2xl shadow-cyan-500/50' : 'hover:scale-105'
                  }`}
                >
                  <Icon className="h-12 w-12 text-cyan-400 mx-auto mb-4" />
                  <div className="text-4xl font-bold bg-gradient-to-r from-cyan-400 to-blue-600 bg-clip-text text-transparent mb-2">
                    {stat.value}
                  </div>
                  <div className="text-gray-400">{stat.label}</div>
                </div>
              );
            })}
          </div>
        </div>
      </section>

      {/* Services Section */}
      <section id="services" className="py-20 bg-gray-900/50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-4xl font-bold text-center mb-16">Hizmetlerimiz</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
            {services.map((service, index) => {
              const Icon = service.icon;
              return (
                <div key={index} className="bg-gradient-to-br from-gray-800 to-gray-900 p-8 rounded-2xl hover:shadow-2xl hover:shadow-cyan-500/20 transition-all duration-300 transform hover:-translate-y-2">
                  <Icon className="h-12 w-12 text-cyan-400 mb-4" />
                  <h3 className="text-2xl font-bold mb-4">{service.title}</h3>
                  <p className="text-gray-400 mb-6">{service.description}</p>
                  <ul className="space-y-2">
                    {service.features.map((feature, idx) => (
                      <li key={idx} className="flex items-center">
                        <Check className="h-5 w-5 text-green-400 mr-2" />
                        <span className="text-gray-300">{feature}</span>
                      </li>
                    ))}
                  </ul>
                </div>
              );
            })}
          </div>
        </div>
      </section>

      {/* Brands Section */}
      <section id="brands" className="py-20">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-4xl font-bold text-center mb-16">Güvenilen Markalar</h2>
          <div className="relative overflow-hidden">
            <div className="flex animate-scroll">
              {[...brands, ...brands].map((brand, index) => (
                <div key={index} className="flex-shrink-0 px-8">
                  <div className="bg-gradient-to-br from-gray-800 to-gray-900 px-8 py-4 rounded-xl text-lg font-semibold hover:shadow-lg hover:shadow-cyan-500/20 transition-all">
                    {brand}
                  </div>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Partnership Models */}
      <section id="partnership" className="py-20 bg-gray-900/50">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-4xl font-bold text-center mb-16">Ortaklık Modellerimiz</h2>
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            {partnershipModels.map((model, index) => (
              <div key={index} className="bg-gradient-to-br from-gray-800 to-gray-900 p-6 rounded-2xl hover:shadow-2xl transition-all duration-300 transform hover:-translate-y-2 group">
                <div className={`h-2 w-20 bg-gradient-to-r ${model.color} rounded-full mb-4 group-hover:w-full transition-all duration-500`}></div>
                <h3 className="text-xl font-bold mb-3">{model.title}</h3>
                <p className="text-gray-400 mb-4 text-sm">{model.description}</p>
                <ul className="space-y-2">
                  {model.features.map((feature, idx) => (
                    <li key={idx} className="flex items-center text-sm">
                      <ChevronRight className="h-4 w-4 text-cyan-400 mr-2" />
                      <span className="text-gray-300">{feature}</span>
                    </li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Process Section */}
      <section className="py-20">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-4xl font-bold text-center mb-16">FOMTIME Süreci</h2>
          <div className="space-y-8">
            {[
              { icon: Target, title: 'Analiz', desc: 'Markanızın mevcut durumunu detaylıca analiz ediyoruz' },
              { icon: Package, title: 'Planlama', desc: 'Size özel büyüme stratejisi oluşturuyoruz' },
              { icon: Zap, title: 'Optimizasyon', desc: 'Tüm süreçlerinizi optimize ediyoruz' },
              { icon: Shield, title: 'Koruma', desc: 'Markanızı yetkisiz satıcılardan koruyoruz' },
              { icon: TrendingUp, title: 'Büyüme', desc: 'Satışlarınızı sürekli artırıyoruz' },
              { icon: BarChart3, title: 'Raporlama', desc: 'Detaylı performans raporları sunuyoruz' }
            ].map((step, index) => {
              const Icon = step.icon;
              return (
                <div key={index} className="flex items-center space-x-4 group">
                  <div className="flex-shrink-0 w-16 h-16 bg-gradient-to-br from-cyan-500 to-blue-600 rounded-full flex items-center justify-center group-hover:scale-110 transition-transform">
                    <Icon className="h-8 w-8" />
                  </div>
                  <div className="flex-grow">
                    <h3 className="text-xl font-bold mb-1">{step.title}</h3>
                    <p className="text-gray-400">{step.desc}</p>
                  </div>
                  {index < 5 && (
                    <div className="flex-shrink-0 hidden md:block">
                      <ArrowRight className="h-6 w-6 text-gray-600" />
                    </div>
                  )}
                </div>
              );
            })}
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="py-20 relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-r from-cyan-600/20 to-blue-600/20"></div>
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center relative z-10">
          <h2 className="text-4xl font-bold mb-6">Markanızı Bir Üst Seviyeye Taşıyalım</h2>
          <p className="text-xl text-gray-300 mb-8">
            E-ticaret dünyasında lider olmak için doğru partner ile çalışın. 
            FOMTIME ile büyüme potansiyelinizi keşfedin.
          </p>
          <button className="bg-gradient-to-r from-cyan-500 to-blue-600 px-10 py-4 rounded-full text-lg font-semibold hover:from-cyan-600 hover:to-blue-700 transition-all transform hover:scale-105 inline-flex items-center">
            Ücretsiz Danışmanlık Al <ArrowRight className="ml-2 h-5 w-5" />
          </button>
        </div>
      </section>

      {/* Contact Section */}
      <section id="contact" className="py-20 bg-gray-900/50">
        <div className="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
          <h2 className="text-4xl font-bold text-center mb-16">İletişime Geçin</h2>
          <div className="bg-gradient-to-br from-gray-800 to-gray-900 p-8 rounded-2xl">
            <form className="space-y-6">
              <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
                <input 
                  type="text" 
                  placeholder="Adınız" 
                  className="bg-gray-800 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-cyan-400"
                />
                <input 
                  type="email" 
                  placeholder="E-posta" 
                  className="bg-gray-800 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-cyan-400"
                />
              </div>
              <input 
                type="text" 
                placeholder="Marka Adı" 
                className="w-full bg-gray-800 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-cyan-400"
              />
              <textarea 
                placeholder="Mesajınız" 
                rows="4" 
                className="w-full bg-gray-800 px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-cyan-400"
              />
              <button className="w-full bg-gradient-to-r from-cyan-500 to-blue-600 py-3 rounded-lg font-semibold hover:from-cyan-600 hover:to-blue-700 transition-all">
                Gönder
              </button>
            </form>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="py-12 border-t border-gray-800">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex flex-col md:flex-row justify-between items-center">
            <div className="flex items-center space-x-2 mb-4 md:mb-0">
              <Sparkles className="h-6 w-6 text-cyan-400" />
              <span className="text-xl font-bold">FOMTIME</span>
            </div>
            <div className="flex space-x-6">
              <a href="#" className="hover:text-cyan-400 transition-colors">Gizlilik</a>
              <a href="#" className="hover:text-cyan-400 transition-colors">Kullanım Koşulları</a>
              <a href="#" className="hover:text-cyan-400 transition-colors">Kariyer</a>
            </div>
          </div>
          <div className="text-center mt-8 text-gray-500">
            © 2024 FOMTIME. Tüm hakları saklıdır.
          </div>
        </div>
      </footer>

      <style jsx>{`
        @keyframes scroll {
          0% { transform: translateX(0); }
          100% { transform: translateX(-50%); }
        }
        
        @keyframes gradient {
          0%, 100% { background-position: 0% 50%; }
          50% { background-position: 100% 50%; }
        }
        
        .animate-scroll {
          animation: scroll 30s linear infinite;
        }
        
        .animate-gradient {
          background-size: 200% 200%;
          animation: gradient 3s ease infinite;
        }
      `}</style>
    </div>
  );
};

export default FomtimeWebsite;
