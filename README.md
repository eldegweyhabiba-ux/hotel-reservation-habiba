# hotel-reservation-habiba

const menuConfig = {
  guest: [
    { label: 'Home', path: '/', icon: 'home' },
    { label: 'Search Rooms', path: '/search', icon: 'search' },
    { label: 'My Bookings', path: '/bookings', icon: 'calendar' },
    { label: 'Profile', path: '/profile', icon: 'user' },
    { label: 'ChatBot', path: '/chat', icon: 'message' }
  ],
  staff: [
    { label: 'Dashboard', path: '/staff', icon: 'dashboard' },
    { label: 'Check-in', path: '/checkin', icon: 'log-in' },
    { label: 'Check-out', path: '/checkout', icon: 'log-out' },
    { label: 'Housekeeping', path: '/housekeeping', icon: 'clean' },
    { label: 'Room Status', path: '/rooms', icon: 'bed' }
  ],
  admin: [
    { label: 'Admin Panel', path: '/admin', icon: 'settings' },
    { label: 'Manage Rooms', path: '/admin/rooms', icon: 'edit' },
    { label: 'Manage Users', path: '/admin/users', icon: 'users' },
    { label: 'Reports', path: '/admin/reports', icon: 'bar-chart' },
    { label: 'System Settings', path: '/admin/settings', icon: 'tool' }
  ]
};


function DynamicMenu({ userRole }) {
  const menuItems = menuConfig[userRole] || menuConfig.guest;
  
  return (
    <nav>
      <ul>
        {menuItems.map(item => (
          <li key={item.path}>
            <a href={item.path}>
              <Icon name={item.icon} /> {item.label}
            </a>
          </li>
        ))}
      </ul>
    </nav>
  );
}
